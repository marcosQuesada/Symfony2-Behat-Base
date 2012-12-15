Symfony Standard Edition
========================
behat --init @AcmeDemoBundle
behat --init src/Acme/DemoBundle


Running bundle features
=======================
behat @AcmeDemoBundle


Running @wip step
=================
behat --tags @wip


Running all scenarios on Symfony 2
==================================

for feature_path in `find src/ -path '*/Features'`; do
    bundle=$(echo $feature_path | sed -e 's/^[^\/]\+\/\([^\/]\+\)\/Bundle\/\([^\/]\+\)\/.*/\1\2/');
    echo "Running suite for $bundle";
    behat $bundle;
done

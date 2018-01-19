---
layout: post
title:  "Tips and tricks for deployer"
date:   2018-01-19 09:00:27 +0100
categories: deployer symfony
---

For symfony 2: `require 'recipe/symfony.php';`
For symfony 3: `require 'recipe/symfony3.php';`

FosJsRouting
If you use FosJsRouting and assetic, you have to execture the fosjsrouting dump commande before dumping assetic.

1. Create the task:
```
task('deploy:dump:jsrouting', function () {
    run('{{bin/php}} {{bin/console}} fos:js-routing:dump {{console_options}}');
});
```
2. Call this task in your deployement script before calling assetic one
```
task('deploy', [
    '...',
    'deploy:assets:install',
    'deploy:dump:jsrouting',
    'deploy:assetic:dump',
    '...',
]);
```
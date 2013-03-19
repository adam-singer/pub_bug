If a package tries to reference 3 packages with the same exact constratins, pub is not able to resolve the version constraints. Another possible issue is better error output on why the constraints are not met. `Could not find a solution that met all version constraints.` is not very helpful. 

```
$ cd pub_bug/package_b/ && pub install
Resolving dependencies...
Could not find a solution that met all version constraints.
```

```
21:02:27-adam@Adams-MacBook-Air:/tmp/pub_bug/package_b
$ pub --verbose install
MSG : Resolving dependencies...
FINE: Adding (entrypoint)'s constraint package_b 0.0.1 (root).
FINE: Changing package_b to version 0.0.1.
FINE: Adding package_b's constraint pathos >=0.4.1 <0.4.2 from hosted (pathos).
IO  : Get versions from https://pub.dartlang.org/packages/pathos.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint html5lib >=0.4.0 <0.4.1 from hosted (html5lib).
IO  : Get versions from https://pub.dartlang.org/packages/html5lib.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint args >=0.4.1 <0.4.2 from hosted (args).
IO  : Get versions from https://pub.dartlang.org/packages/args.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint bot >=0.15.0 <0.16.0 from hosted (bot).
IO  : Get versions from https://pub.dartlang.org/packages/bot.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint package_aaa any from path ({path: /private/tmp/pub_bug/package_b/../package_aaa/, relative: true}).
FINE: Adding package_b's constraint meta >=0.4.1 <0.4.2 from hosted (meta).
IO  : Get versions from https://pub.dartlang.org/packages/meta.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint logging >=0.4.1 <0.4.2 from hosted (logging).
IO  : Get versions from https://pub.dartlang.org/packages/logging.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint browser >=0.4.1 <0.4.2 from hosted (browser).
IO  : Get versions from https://pub.dartlang.org/packages/browser.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint package_aa any from path ({path: /private/tmp/pub_bug/package_b/../package_aa/, relative: true}).
FINE: Adding package_b's constraint unittest >=0.4.1 <0.4.2 from hosted (unittest).
IO  : Get versions from https://pub.dartlang.org/packages/unittest.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint source_maps >=0.4.0 <0.4.1 from hosted (source_maps).
IO  : Get versions from https://pub.dartlang.org/packages/source_maps.json.
FINE: Got response 200 OK.
FINE: Adding package_b's constraint package_a any from path ({path: /private/tmp/pub_bug/package_b/../package_a/, relative: true}).
FINE: Changing pathos to version 0.4.1.
IO  : Describe package at https://pub.dartlang.org/packages/pathos/versions/0.4.1.yaml.
FINE: Got response 200 OK.
FINE: Changing html5lib to version 0.4.0.
IO  : Describe package at https://pub.dartlang.org/packages/html5lib/versions/0.4.0.yaml.
FINE: Got response 200 OK.
FINE: Changing args to version 0.4.1.
IO  : Describe package at https://pub.dartlang.org/packages/args/versions/0.4.1.yaml.
FINE: Got response 200 OK.
FINE: Changing bot to version 0.15.0+2.
IO  : Describe package at https://pub.dartlang.org/packages/bot/versions/0.15.0%2B2.yaml.
FINE: Got response 200 OK.
FINE: Changing package_aaa to version 0.0.1.
FINE: Changing meta to version 0.4.1+1.
IO  : Describe package at https://pub.dartlang.org/packages/meta/versions/0.4.1%2B1.yaml.
FINE: Got response 200 OK.
FINE: Changing logging to version 0.4.1+1.
IO  : Describe package at https://pub.dartlang.org/packages/logging/versions/0.4.1%2B1.yaml.
FINE: Got response 200 OK.
FINE: Changing browser to version 0.4.1.
IO  : Describe package at https://pub.dartlang.org/packages/browser/versions/0.4.1.yaml.
FINE: Got response 200 OK.
FINE: Changing package_aa to version 0.0.1.
FINE: Changing unittest to version 0.4.1.
IO  : Describe package at https://pub.dartlang.org/packages/unittest/versions/0.4.1.yaml.
FINE: Got response 200 OK.
FINE: Changing source_maps to version 0.4.0.
IO  : Describe package at https://pub.dartlang.org/packages/source_maps/versions/0.4.0.yaml.
FINE: Got response 200 OK.
FINE: Changing package_a to version 0.0.1.
FINE: Adding html5lib's constraint browser >=0.3.2 from hosted (browser).
FINE: Adding html5lib's constraint unittest any from hosted (unittest).
FINE: Adding html5lib's constraint source_maps >=0.4.0 <0.4.1 from hosted (source_maps).
FINE: Adding html5lib's constraint meta any from hosted (meta).
FINE: Adding args's constraint unittest any from hosted (unittest).
FINE: Adding bot's constraint html5lib >=0.3.3+2 from hosted (html5lib).
FINE: Adding bot's constraint args >=0.4.1 from hosted (args).
FINE: Adding bot's constraint browser >=0.4.1 from hosted (browser).
FINE: Adding bot's constraint meta >=0.4.1+1 from hosted (meta).
IO  : Get versions from https://pub.dartlang.org/packages/meta.json.
FINE: Got response 200 OK.
FINE: Adding bot's constraint logging >=0.4.1 from hosted (logging).
FINE: Adding bot's constraint unittest >=0.4.1 from hosted (unittest).
FINE: Adding bot's constraint pathos >=0.4.1 from hosted (pathos).
FINE: Adding package_aaa's constraint html5lib >=0.4.0 <0.4.1 from hosted (html5lib).
FINE: Adding package_aaa's constraint browser >=0.4.1 <0.4.2 from hosted (browser).
FINE: Adding package_aaa's constraint args >=0.4.1 <0.4.2 from hosted (args).
FINE: Adding package_aaa's constraint bot >=0.15.0 <0.16.0 from hosted (bot).
FINE: Adding package_aaa's constraint meta >=0.4.1 <0.4.2 from hosted (meta).
FINE: Adding package_aaa's constraint logging >=0.4.1 <0.4.2 from hosted (logging).
FINE: Adding package_aaa's constraint unittest >=0.4.1 <0.4.2 from hosted (unittest).
FINE: Adding package_aaa's constraint source_maps >=0.4.0 <0.4.1 from hosted (source_maps).
FINE: Adding package_aaa's constraint pathos >=0.4.1 <0.4.2 from hosted (pathos).
FINE: Adding logging's constraint unittest any from hosted (unittest).
FINE: Adding logging's constraint meta any from hosted (meta).
FINE: Adding package_aa's constraint html5lib >=0.4.0 <0.4.1 from hosted (html5lib).
FINE: Adding package_aa's constraint browser >=0.4.1 <0.4.2 from hosted (browser).
FINE: Adding package_aa's constraint args >=0.4.1 <0.4.2 from hosted (args).
FINE: Adding package_aa's constraint bot >=0.15.0 <0.16.0 from hosted (bot).
FINE: Adding package_aa's constraint meta >=0.4.1 <0.4.2 from hosted (meta).
FINE: Adding package_aa's constraint logging >=0.4.1 <0.4.2 from hosted (logging).
FINE: Adding package_aa's constraint unittest >=0.4.1 <0.4.2 from hosted (unittest).
FINE: Adding package_aa's constraint source_maps >=0.4.0 <0.4.1 from hosted (source_maps).
FINE: Adding package_aa's constraint pathos >=0.4.1 <0.4.2 from hosted (pathos).
FINE: Adding unittest's constraint meta any from hosted (meta).
FINE: Adding source_maps's constraint unittest any from hosted (unittest).
FINE: Adding package_a's constraint html5lib >=0.4.0 <0.4.1 from hosted (html5lib).
FINE: Adding package_a's constraint browser >=0.4.1 <0.4.2 from hosted (browser).
FINE: Adding package_a's constraint args >=0.4.1 <0.4.2 from hosted (args).
FINE: Adding package_a's constraint bot >=0.15.0 <0.16.0 from hosted (bot).
FINE: Adding package_a's constraint meta >=0.4.1 <0.4.2 from hosted (meta).
FINE: Clean up system cache temp directory /Users/adam/.pub-cache/_temp.
ERR : Could not find a solution that met all version constraints.
```

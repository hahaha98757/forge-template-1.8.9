# Architectury Loom based template for 1.8.9 forge mods

## Usage

Check out https://moddev.nea.moe/ for a full tutorial on legacy modding.

Alternatively, read here for a basic overview on how to use this repository.

To get started, [Use this template](https://github.com/new?template_name=forge-template-1.8.9&template_owner=hahaha98757).

> [!WARNING]
> You need to change the contents of some files.
> In the 'gradle.properties' file, change 'baseGroup' and 'modid' appropriately.
> In the 'settings.gradle.kts' file, change line 26 (rootProject.name = "examplemod") appropriately.
> Change 'ExampleMod.java', 'AutoDiscoveryMixinPlugin.java', 'MixinGuiMainMenu.java', and 'mcmod.info' file appropriately. Rename "examplemod" of 'mixins.examplemod.json' file to your mod's modid.
 

This project uses [DevAuth](https://github.com/DJtheRedstoner/DevAuth) per default, so you can log in using your real
minecraft account. If you don't need that, you can remove it from the buildscript.

To run the mod you will need two JDKs, one Java 17 jdk and one Java 1.8 jdk. You can download those
from [here](https://adoptium.net/temurin/releases) (or use your own downloads).

When you import your project into IntelliJ, you need to set the gradle jvm to the Java 17 JDK in the gradle tab, and the
Project SDK to the Java 1.8 JDK. Then click on the sync button in IntelliJ, and it should create a run task
called `Minecraft Client`. If it doesn't then try relaunching your IntelliJ. **Warning for Mac users**: You might have to remove the `-XStartOnFirstThread` vm argument from your run configuration. In the future, that should be handled by the plugin, but for now you'll probably have to do that manually.

To export your project, run the `gradle build` task, and give other people the
file `build/libs/<modid>-<version>.jar`. Ignore the jars in the `build/badjars` folder. Those are intermediary jars that
are used by the build system but *do not work* in a normal forge installation.

If you don't want mixins (which allow for modifying vanilla code), then you can remove the references to mixins from
the `build.gradle.kts` at the lines specified with comments and the `com.examplemod.mixin` package.

If you don't want access transformers (which allow for making methods public/non-final) you can delete the
`accesstransformer.cfg` file. If you make a change to the `accesstransformers.cfg` you might need to rebuild your
project using `./gradlew build --refresh-dependencies`.

### For those who have not an attention span

[![Youtube Tutorial](https://i.ytimg.com/vi/nWzHlomdCgc/maxresdefault.jpg)](https://www.youtube.com/watch?v=nWzHlomdCgc)

## Licensing

This template is licensed under the Unlicense (license copy present in this repository), or alternatively under [Creative Commons 1.0 Universal (CC0 1.0)](https://creativecommons.org/publicdomain/zero/1.0/), and all contributions and PR to this template are expected to follow this. This means your mod, based on this template can be licensed whatever way you want, and does not need to reference back to this template in any way.

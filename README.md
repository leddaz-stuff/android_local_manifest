# StatiX Minimal
To build statix minimal, sync AOSP master using
```bash
mkdir statix-minimal && cd statix-minimal
repo init -u https://android.googlesource.com/platform/manifest -b main --depth 1
git clone https://github.com/statix-minimal/android_local_manifest .repo/local_manifests
repo sync -j$(nproc --all)
```

To build (Replace devicename with your synced device tree codenames)

```bash
lunch statix_devicename-trunk_staging-user
m updatepackage
```

Your build should be available in `out/target/product/devicename/`
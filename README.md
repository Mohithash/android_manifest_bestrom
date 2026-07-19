# android_manifest_bestrom

**Full BestROM A17 platform manifest** — GrapheneOS model (full AOSP + thin product).

| Layer | Source |
|-------|--------|
| Platform | Google AOSP `android-17.0.0_r1` (complete `default.xml`) |
| Product | `vendor/bestrom` → [android_vendor_bestrom](https://github.com/Mohithash/android_vendor_bestrom/tree/17) |
| Device | local only → `snippets/local_manifest_peridot.xml` |

**Not** Evolution X / Lineage-24. Pure AOSP + monochrome battery product.

## Init

```bash
mkdir ~/bestrom-a17 && cd ~/bestrom-a17
repo init -u https://github.com/Mohithash/android_manifest_bestrom -b 17 --git-lfs
mkdir -p .repo/local_manifests
curl -L -o .repo/local_manifests/peridot.xml \
  https://raw.githubusercontent.com/Mohithash/android_manifest_bestrom/17/snippets/local_manifest_peridot.xml
repo sync -c -j$(nproc) --force-sync --no-clone-bundle --no-tags
. build/envsetup.sh
source vendor/bestrom/build/envsetup.sh
bestrom_lunch peridot userdebug
m bacon
```

## Design / logos

https://github.com/Mohithash/bestrom-project

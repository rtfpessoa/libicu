# libicu

```
apt -y update && apt -y install curl binutils zstd
curl -fsSL http://ports.ubuntu.com/pool/main/i/icu/libicu70_70.1-2ubuntu1_arm64.deb -o icu_arm64.deb
mkdir -p icu_arm64/data
ar x icu_arm64.deb --output=icu_arm64
tar -acf icu_arm64/data.tar.zst -C icu_arm64/data
curl -fsSL http://es.archive.ubuntu.com/ubuntu/pool/main/i/icu/libicu70_70.1-2_amd64.deb -o icu_amd64.deb
mkdir -p icu_amd64/data
ar x icu_amd64.deb --output=icu_amd64
tar -acf icu_amd64/data.tar.zst -C icu_amd64/data
mkdir icu_data
cp -rf icu_arm64/data/* icu_data/
cp -rf icu_amd64/data/* icu_data/
tar -cvf icu_data.tar.gz -C icu_data .
```

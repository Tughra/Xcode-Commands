# Xcode-Commands
pods etc. commands


## When plugin error
```sh
rm -rf Pods
rm -rf Podfile.lock
rm -rf ~/.pub-cache/hosted/pub.dartlang.org/
pod cache clean --all
pod repo update
flutter clean
flutter pub get
```

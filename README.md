# Flutter-Commands
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
## Flutter different version usage

To create an alias you need to create .bash_aliases file inside your $HOME directory

1) You can do this via a terminal by running
```sh
nano ~/.bash_aliases
```
Note that you can name the aliases as you like.

I have used the name

flutterd to point to flutter_dev
flutterm to point to flutter_master
flutterb to point to flutter_beta
That means when you type flutterd in the terminal then it will use the SDK located at ~/Documents/flutter_dev/bin/flutter and respectively for rest of the aliases.

(Hit Ctrl + X and enter to save and exit.)

2)And lastly, you need to add this in your shell file
```sh
if [ -f ~/.bash_aliases ]; then
. ~/.bash_aliases
fi
```
which is basically the rc file

$HOME/.bashrc if you are using Bash.

$HOME/.zshrc file if you are using Z shell (executable zsh)

if you are not sure then typing echo $SHELL in your Terminal tells you which shell you’re using. This is the same file where you have added your Flutter SDK's path when you first installed it. And if the file doesn't exist you may create it

3)Run source $HOME/.<rc file> to refresh the current terminal window.

Now you can verify by typing your alias names in the terminal flutterm, flutterd, etc. and it will respond from the respective SDK.

You can verify this by running <alias name> doctor -v.

For example, to verify flutterd is pointing to dev, run flutterd doctor -v.


Eğer path olarak eklenmez ise flutter3_13_8 doctor -v komutunu çalıştırdıktan sonra
 Warning: `flutter` on your path resolves to
      /Users/apple/flutter/bin/flutter, which is not inside your current Flutter
      SDK checkout at /Users/apple/flutter_3_13_8. Consider adding
      /Users/apple/flutter_3_13_8/bin to the front of your path.
uyarısı verecektir. Bu uyarı aşağıdaki gibi path eklendikten sonra ortadan kalkar.

## Kalıcı olarak path ekleme Mac

```sh
export PATH=[PATH_OF_FLUTTER_GIT_DIRECTORY]/bin:$PATH
```
```sh
export PATH=/Users/apple/flutter_3_13_8/bin:$PATH
```

PATH değişkenini kalıcı olarak güncellemek için profil dosyanıza (~/.bashrc, ~/.zshrc veya benzeri) yukarıdaki export komutunu ekleyebilirsiniz. 
Bu sayede her terminal oturumu başladığında otomatik olarak eklenmiş olacaktır.

Yada direkt yazarak da eklenebilir.
```sh
echo 'export PATH=/Users/apple/flutter_3_13_8/bin:$PATH' >> ~/.zshrc
```
bashrc için
```sh
echo 'export PATH=/Users/apple/flutter_3_13_8/bin:$PATH' >> ~/.bashrc
```

$HOME görüntülemek için
```sh
echo $HOME
```






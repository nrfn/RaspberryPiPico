# Raspberry Pi sPico
RaspberryPiPico学習用リポジトリ

# C言語の環境構築
- ターミナルからコンパイラをインストール\
Macの場合 : `xcode-select --install`

- VSCodeの拡張機能`C/C++`をインストール。

- コンパイル
Macの場合、標準でターミナルから`clang`コマンドを実行するとコンパイルできる。
```
clang -o 出力ファイル名 コンパイル対象ファイル
```

-  実行
ターミナルからパスとコンパイルされたファイル名でプログラムを実行できる。

# Raspberry Pi Picoの環境構築
- CMake のインストール\
CMake はプロジェクトのビルドを管理するツールです。
```
brew install cmake
```

- GCC ARM クロスコンパイラのインストール\
`arm-none-eabi-gcc`は ARM マイクロコントローラ用のクロスコンパイラです。
```
brew tap ArmMbed/homebrew-formulae
brew install arm-none-eabi-gcc
```

- Pico SDK のクローン
Pico SDK を GitHub からクローンします。
```
git clone -b master https://github.com/raspberrypi/pico-sdk.git
```

- pico-examples のクローン
pico-examples リポジトリもクローンします。
```
git clone -b master https://github.com/raspberrypi/pico-examples.git
```

- Pico SDK のサブモジュールを初期化
Pico SDK のサブモジュールを初期化します。
```
cd pico-sdk
git submodule update --init
```

- 環境変数の設定
PICO_SDK_PATH 環境変数を設定して、Pico SDK のパスを指定。\
これをシェルの設定ファイル（例: .zshrc）に追加する。
```
export PICO_SDK_PATH=/path/to/pico-sdk
```
`/path/to/pico-sdk`はPico SDK をクローンしたディレクトリのフルパスに置き換えてください。
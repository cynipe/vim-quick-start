======
README
======

入っているプラグイン
====================

:gmarik/vundle:           Plugin管理
:Shougo/unite.vim:        色々なコマンドを統合するプラグイン
:Shougo/neocomplcache:    補完Plugin
:h1mesuke/unite-outline:  ファイルアウトライン表示Plugin
:scrooloose/nerdtree:     EclipseのPackage Explore的にディレクトリを表示してくれるPlugin
:tpope/vim-fugitive:      Git連携Plugin
:vim-coffee-script:       CoffeeScript用Plugin
:Lokaltog/vim-powerline:  ステータスラインをカッコよくする

インストール方法
================

 #. まずこのリポジトリとvundleをクローンする::

    git clone https://github.com/cynipe/vim-quick-start.git ~/dotfiles/vim
    git clone https://github.com/gmarik/vundle.git ~/dotfiles/vim/.vim/bundle/vundle

 #. OS毎に後述の方法でシンボリックリンク等を貼る
 #. GVimを起動し、エラーは無視して:BundleInstallを実行

Linux, OSX
----------

::

  ln -sF ~/dotfiles/.vimrc $HOME
  ln -sF ~/dotfiles/.vim $HOME

WindowsXP
---------

http://technet.microsoft.com/en-us/sysinternals/bb896768.aspx からjunctionをダウンロードしてインストールする(PATHを通せばOK)

::

  md %USERPROFILE%\_vimfiles
  junction %USERPROFILE%\_vimrc %USERPROFILE%\.vimrc
  junction %USERPROFILE%\_vimfiles %USERPROFILE%\.vim


Windows Vista以降
-----------------

::

  mklink %USERPROFILE%\_vimrc ~/dotfiles/.vimrc
  mklink \d %USERPROFILE%\_vimfiles ~/dotfiles/.vim


使い方
======

ベーシック
----------

<C-i>
  ヘルプを開く
<C-i><C-i>
  カーソル下のキーワードのヘルプを表示
:Ev
  vimrcを開く
:Rv
  vimrcをその場でリロード

移動
----

<C-a>
  行頭に移動(^と同じ)
<C-e>
  行末に移動($と同じ)
<C-v>
  矩形選択
<S-v>
  行選択
[
  対応する括弧に移動
]
  対応する括弧に移動
vv
  カーソル位置から行末まで選択

編集
----

<C-x>
  行末の空白を除去する
<C-z>
  tabをスペースに変換する

編集
----

:Cp932
  CP932でファイルを開き直す
:Eucjp
  EUCJPでファイルを開き直す
:Iso2022jp
  ISO2022JPでファイルを開き直す
:Utf8
  UTF-8でファイルを開き直す
:Jis
  JISでファイルを開き直す
:Sjis
  SJISでファイルを開き直す

補完
----

neocomplcacheの機能

補完表示時に<C-y>
  書いた文字はそのままに補完をキャンセル
補完表示時に<C-e>
  書いた文字を削除して補完をキャンセル

Eclipseのパッケージエクスプローラ的なもの
-----------------------------------------

NERDTreeの機能

<S-t>
  エクスプローラを開く/閉じる
エクスプローラ上で<C-i>
  隠しファイルも表示
エクスプローラ上でma
  空ファイルを新規作成。

  名前の末尾を/で終わらせるとディレクトリ作成
エクスプローラ上でmm
  対象ファイル(ディレクトリ)を移動
エクスプローラ上でmd
  対象ファイル(ディレクトリ)を削除

  ディレクトリ削除の場合はyesと入力しない限り削除されない。
  通常ファイルはy
エクスプローラ上でr
  システムのファイラ(エクスプローラ、Finder)を開く
エクスプローラ上で<S-r>
  リフレッシュ
エクスプローラ上でo
  ファイルを開く

  ディレクトリの場合展開
エクスプローラ上でv
  水平分割で開く
エクスプローラ上でs
  垂直分割で開く

EclipseのOpen Resource(Ctrl+Alt+R)
----------------------------------

Unite.vimの機能

ff
  カレントディレクトリをベースにファイル一覧を表示
fb
  バッファ一覧を表示
fu
  最近使ったファイル一覧を表示
fd
  現在のバッファのカレントディレクトリからファイル一覧
一覧表示時にq
  開いている一覧を閉じる
一覧表示時に<ESC><ESC>
  開いている一覧を閉じる
一覧表示時にjj
  開いている一覧上で選択モードになる
  jjしたあとはjkで上下移動可
一覧でファイル選択時に<C-l>
  開きたいファイル上で実行すると水平分割で開く
一覧でファイル選択時に<C-v>
  開きたいファイル上で実行すると垂直分割で開く

git操作関連
-----------

fugtiv.vimの機能

<Space>gd
  編集中のファイルに対してgit diff
<Space>gs
  git statusを表示
<Space>gl
  git logを表示
<Space>ga
  編集中のファイルをgit add
<Space>gc :<C-u>Gcommit<Enter>
  git commit
<Space>gC :<C-u>Git commit --amend<Enter>
  git commit --amend
<Space>gb
  編集中のファイルに対してgit blame

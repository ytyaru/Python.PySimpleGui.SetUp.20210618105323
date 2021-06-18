# 絵文字フォントを使うとTkinterがバグでエラーになって使えない

　これはひどい。

<!-- more -->

# 情報源

* [x-error-of-failed-request-badlength-poly-request-too-large-or-internal-xlib-le](https://askubuntu.com/questions/1236488/x-error-of-failed-request-badlength-poly-request-too-large-or-internal-xlib-le)
* [1852985](https://bugs.launchpad.net/ubuntu/+source/git/+bug/1852985)
* [display-emoji-in-tkinter](https://stackoverflow.com/questions/55792234/display-emoji-in-tkinter)

# コマンド

```sh
python3 -m tkinter
```
```sh
X Error of failed request:  BadLength (poly request too large or internal Xlib length error)
  Major opcode of failed request:  139 (RENDER)
  Minor opcode of failed request:  20 (RenderAddGlyphs)
  Serial number of failed request:  125
  Current serial number in output stream:  162
```

# 対処

　絵文字フォントをアンインストールする。

　私の場合、以下のように`fonts-noto-color-emoji`絵文字フォントをインストールしていた。これを削除せよとのこと。

* [Unicodeの絵文字を表示させる](https://ytyaru.hatenablog.com/entry/2022/12/29/000000)

# 所感

　やだよ。なんでTkのためにフォントをアンインストールしないといけないんだよ。絵文字フォントは使いたいんだよ。Tk、お前なんかよりずっとな。Tkのほうがフォントによりクラッシュしなくなるよう改修すべきだろ。それができないなら、もうTkなんて使わない。さらばTk。

# 対象環境

* <time datetime="2021-06-18T10:33:23+0900" title="実施日">2021-06-18</time>
* [Raspbierry pi](https://ja.wikipedia.org/wiki/Raspberry_Pi) 4 Model B
* [Raspberry Pi OS](https://ja.wikipedia.org/wiki/Raspbian) buster 10.0 2020-08-20 [※](http://ytyaru.hatenablog.com/entry/2020/10/06/111111)
* [bash](https://ja.wikipedia.org/wiki/Bash) 5.0.3(1)-release

```sh
$ uname -a
Linux raspberrypi 5.4.83-v7l+ #1379 SMP Mon Dec 14 13:11:54 GMT 2020 armv7l GNU/Linux
```

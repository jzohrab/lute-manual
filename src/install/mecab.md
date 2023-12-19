> Note: this is for non-Docker users studying Japanese only (or devs who are working on Lute)

Lute users who are studying Japanese will need to install MeCab and an appropriate dictionary for parsing Japanese text.  If MeCab is not installed or not on your PATH, you will not be able to parse Japanese texts.

# Installation

## Mac

You can install MeCab and a dictionary using `homebrew`.

If you don't have homebrew installed, then first [get homebrew](https://brew.sh/).  Then:

```
brew install mecab
brew install mecab-ipadic
```

## Windows

The link [https://taku910.github.io/mecab/](https://taku910.github.io/mecab/) has a link under Binary package for MS-Windows: mecab-0.996.exe: [ダウンロード](https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7WElGUGt6ejlpVXc).  Verify this link and download.

If your system is 64 bit, or the above MeCab is not working, try downloading from this link instead: [MeCab 64bit](https://github.com/ikegami-yukino/mecab/releases/download/v0.996.2/mecab-64-0.996.2.exe)

When installing MeCab, choose the **UTF-8** charset (I'm not sure if another charset will work).

After installation, add the MeCab bin path -- usually it's `C:\Program Files\MeCab\bin` -- to the `PATH` environment variable.  If you don't know how to edit the Environment Variables, see this video: [How to Set Environment Variables in Windows 11](https://www.youtube.com/watch?v=ow2jROvxyH4).

## Linux

Use apt-get:

```
sudo apt-get update -y
sudo apt-get install -y mecab mecab-ipadic-utf8
```

# Verification

Test mecab from the terminal:

```
$ mecab
すもももももももものうち
すもも    名詞,一般,*,*,*,*,すもも,スモモ,スモモ
も    助詞,係助詞,*,*,*,*,も,モ,モ
もも    名詞,一般,*,*,*,*,もも,モモ,モモ
```

Windows users may need to type the full path.

# Lute configuration

If everything is installed correctly, you will see a Japanese sample story when you start Lute.  If you _don't_ see that story, then either your MeCab isn't set up correctly, or Lute can't find it.

Lute uses a library called [natto-py](https://github.com/buruzaemon/natto-py) that _usually_ finds and uses MeCab automatically.  If it can't, you'll need to specify the path to your MeCab library in Lute's Settings (top right menu bar).  There is a box for you to enter your MeCab path and do a test parse.  If that test succeeds, you're good to go.  If not, jump into the Lute Discord.

## Sample `MECAB_PATH` values

> The [natto-py](https://github.com/buruzaemon/natto-py) gives a few possibilities for the path, which may just be examples and not really valid.

| System | MECAB_PATH |
| --- | --- |
| Mac OS | `/usr/local/Cellar/mecab/0.996/lib/libmecab.dylib` |
| bash on UNIX/Linux | `/usr/local/lib/libmecab.so` |
| Windows | `C:\Program Files\MeCab\bin\libmecab.dll` |
| Lute's docker container | `/lib/aarch64-linux-gnu/libmecab.so.2` |
| Linux Mint | `/lib/x86_64-linux-gnu/libmecab.so.2` |


## Finding the mecab library

> These are various notes about finding MeCab, hopefully it will help you find your MeCab library.

When setting up MeCab in Docker and GitHub, I found the mecab library like this:

```
which mecab

# make note of the path, then:
ldd </path/returned/by/which/mecab>
```

returned:

```
linux-vdso.so.1 (0x00007ffd280a8000)
libmecab.so.2 => /lib/x86_64-linux-gnu/libmecab.so.2 (0x00007f9fe7cdf000)
libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f9fe7a00000)
libstdc++.so.6 => /lib/x86_64-linux-gnu/libstdc++.so.6 (0x00007f9fe7600000)
libm.so.6 => /lib/x86_64-linux-gnu/libm.so.6 (0x00007f9fe7919000)
/lib64/ld-linux-x86-64.so.2 (0x00007f9fe7dc4000)
libgcc_s.so.1 => /lib/x86_64-linux-gnu/libgcc_s.so.1 (0x00007f9fe7cbb000)
```

For this OS, the correct library was actually `libmecab.so.2`.

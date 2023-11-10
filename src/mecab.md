> Note: this is for non-Docker users studying Japanese only (or devs who are working on Lute)

Lute users who are studying Japanese will need to install MeCab and an appropriate dictionary for parsing Japanese text.  If MeCab is not installed or not on your PATH, you will not be able to parse Japanese texts.

# Installation

## Mac

You can install MeCab and a dictionary using `homebrew`:

```
brew install mecab
brew install mecab-ipadic
```

## Windows

> instructions needed!

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
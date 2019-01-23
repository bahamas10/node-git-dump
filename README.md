 [![Rawsec's CyberSecurity Inventory](https://inventory.rawsec.ml/img/badges/Rawsec-inventoried-FF5050_flat.svg)](https://inventory.rawsec.ml/tools.html#git-dump)
 [![GitHub stars](https://img.shields.io/github/stars/bahamas10/node-git-dump.svg)](https://github.com/bahamas10/node-git-dump/stargazers)
 [![GitHub license](https://img.shields.io/github/license/bahamas10/node-git-dump.svg)](https://github.com/bahamas10/node-git-dump)
 

git-dump
========

Dump the contents of a remote git repository without directory listing enabled

Based on [GitDumper](https://github.com/internetwache/GitTools/blob/master/Dumper/gitdumper.sh) but
rewritten to not rely on specific GNU grep options

Installation
------------

First, install [Node.js](http://nodejs.org), then:

    npm install -g git-dump

Usage
-----

    git-dump <url> [dir=.] [workers=3]

Example
-------

Using Blizzards Lumerico website for the Sombra ARG

    $ ./git-dump https://lumerico.mx/president-bypass/.git sombra
    > GET https://lumerico.mx/president-bypass/.git/description --> description
    > GET https://lumerico.mx/president-bypass/.git/HEAD --> HEAD
    > GET https://lumerico.mx/president-bypass/.git/config --> config
    > GET https://lumerico.mx/president-bypass/.git/index --> index
    > GET https://lumerico.mx/president-bypass/.git/refs/heads/master --> refs/heads/master
    found 1 hashes in refs/heads/master
    > GET https://lumerico.mx/president-bypass/.git/logs/HEAD --> logs/HEAD
    found 2 hashes in logs/HEAD
    > GET https://lumerico.mx/president-bypass/.git/logs/refs/heads/master --> logs/refs/heads/master
    found 2 hashes in logs/refs/heads/master
    > GET https://lumerico.mx/president-bypass/.git/info/exclude --> info/exclude
    > GET https://lumerico.mx/president-bypass/.git/objects/67/7d90499d571221e2ec71914e56aee35afa9340 --> objects/67/7d90499d571221e2ec71914e56aee35afa9340
    found 1 hashes in `git cat-file -p 677d90499d571221e2ec71914e56aee35afa9340`
    objects/67/7d90499d571221e2ec71914e56aee35afa9340 already downloaded
    > GET https://lumerico.mx/president-bypass/.git/objects/67/7d90499d571221e2ec71914e56aee35afa9340 --> objects/67/7d90499d571221e2ec71914e56aee35afa9340
    found 1 hashes in `git cat-file -p 677d90499d571221e2ec71914e56aee35afa9340`
    > GET https://lumerico.mx/president-bypass/.git/objects/7e/1701a6431539487bb0faf2862059c7aab7bc98 --> objects/7e/1701a6431539487bb0faf2862059c7aab7bc98
    found 4 hashes in `git cat-file -p 7e1701a6431539487bb0faf2862059c7aab7bc98`
    > GET https://lumerico.mx/president-bypass/.git/objects/7e/1701a6431539487bb0faf2862059c7aab7bc98 --> objects/7e/1701a6431539487bb0faf2862059c7aab7bc98
    found 4 hashes in `git cat-file -p 7e1701a6431539487bb0faf2862059c7aab7bc98`
    > GET https://lumerico.mx/president-bypass/.git/objects/79/e2fa35af7d9fee7961bee8d61ed096860f3b35 --> objects/79/e2fa35af7d9fee7961bee8d61ed096860f3b35
    > GET https://lumerico.mx/president-bypass/.git/objects/54/273bcc08ed806cb37e3c6d3e146c2a17744964 --> objects/54/273bcc08ed806cb37e3c6d3e146c2a17744964
    objects/54/273bcc08ed806cb37e3c6d3e146c2a17744964 already downloaded
    objects/79/e2fa35af7d9fee7961bee8d61ed096860f3b35 already downloaded
    > GET https://lumerico.mx/president-bypass/.git/objects/91/141f7bb072c3305c727c471e628358b23b6b48 --> objects/91/141f7bb072c3305c727c471e628358b23b6b48
    > GET https://lumerico.mx/president-bypass/.git/objects/07/521638776e9f959c311373512aa87a58bfd570 --> objects/07/521638776e9f959c311373512aa87a58bfd570
    > GET https://lumerico.mx/president-bypass/.git/objects/91/141f7bb072c3305c727c471e628358b23b6b48 --> objects/91/141f7bb072c3305c727c471e628358b23b6b48
    > GET https://lumerico.mx/president-bypass/.git/objects/07/521638776e9f959c311373512aa87a58bfd570 --> objects/07/521638776e9f959c311373512aa87a58bfd570

Now, the directory will resemble a git repo

    $ cd sombra/
    $ ls
    HEAD         config       description  index        info/        logs/        objects/     refs/
    $ git log
    commit 677d90499d571221e2ec71914e56aee35afa9340
    Author: pedro <pedro@lumerico.mx>
    Date:   Wed Oct 12 20:09:41 2016 -0400

        president auth bypass
        
        Signed-off-by: pedro <pedro@lumerico.mx>

License
-------

MIT

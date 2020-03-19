# cppbook
「C++の入門書(の予定)」のフォーク

## 仕様
Markdownからウェブドキュメントを作成するライブラリ、[MkDocs](https://www.mkdocs.org/)を使用。
### 参考リンク
- [Qiita:MkDocsによるドキュメント作成](https://qiita.com/mebiusbox2/items/a61d42878266af969e3c)
- [Qiita:カンタンにドキュメントが作れるmkdocsをはじめてみよう](https://qiita.com/wamisnet/items/ed725d74f945f7c06b91)
- [MkDocs公式(英語)](https://www.mkdocs.org/)
### 追加プラグインについて
現在のバージョンでは、より柔軟にドキュメントを作成するため、いくつか外部プラグインをインストールしている。
- mkdocs-material
- Pygments
- python-markdown-math

これらはどれもpip(Python純正のパッケージマネージャ)で簡単にインストールすることができる。
上に記載した、インストールの際に使うレポジトリの名前は、実際にmkdocs.yml内で呼び出す際の名前とは異なる可能性があるので注意する。
例:mkdocs-material→material

### MkDocsコマンドチートシート
新しいドキュメントを作成する:``mkdocs new [name]``
WEBページをまるごと生成:``mkdocs build``
ローカルホスト(serve中は自動リビルド):``mkdocs serve``
設定すればGitHub Pagesにデプロイできるらしい:``mkdocs gh-deploy``

## 階層構造
``mkdocs new document``というコマンドでドキュメントを作ったという設定で。
ただしsiteディレクトリは一度ビルドしないと現れない。
```
document/
    ┣ mkdocs.yml
    ┣ docs/
    ┃   ┣ css/
    ┃   ┣ img/
    ┃   ┣ index.md
    ┃　 ┗ etc...
    ┗site/
        ┣ index.html
        ┣ assets/
        ┣ css/
        ┣ img/
        ┣ search/
        ┗ etc...
```
``mkdocs.yml``内で指定する追加CSSや、Markdownファイルで呼び出す画像ファイルはdocsディレクトリに置くとよい。
``mkdocs.yml``でCSSやスクリプトを指定する際は、``mkdocs.yml``の存在するディレクトリではなく一つ下のdocsディレクトリから見た相対パスで指定する。
CDNから引っ張ってくるならURLだから問題ないけれど。

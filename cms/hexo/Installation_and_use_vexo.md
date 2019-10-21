# hexoに戻ってきた

19/10/14に、4.0.0 にメジャーアップデートしてた  
なんかプラグインとかテーマとかいろいろ増えてる印象

GCPで、とかもいけるらしい  
https://www.okina-freelife.page/20190822/blog_hexo_intro/

liquidでもいけるらしい  
hexo-renderer-liquid - npm  
https://www.npmjs.com/package/hexo-renderer-liquid

## 触ってみる
一旦、vexo っていうテーマが vue テイストで美しいのでそれで行ってみる  

yanm1ng/hexo-theme-vexo: 🍟 Vexo is a Hexo theme inspired by Vue's official website.  
https://github.com/yanm1ng/hexo-theme-vexo  

なんかテーマ「Vexo」のところはそのまま訳💦  

### hexo-cliインストール・プロジェクト初期化
```
$ yarn global add hexo-cli
$ hexo init <Directory>
```

### Live reloadしたいので、hexo-browsersync いれておく
```
$ yarn add hexo-browsersync
$ hexo server --draft --open
```

### テーマ「Vexo」のインストールと設定
```
$ hexo init <Directory>
$ cd <Directory>
$ git clone https://github.com/yanm1ng/hexo-theme-vexo.git themes/vexo
$ cp -R themes/vexo/_source/* source/
```
``_config.yml``の``theme``を設定  
```
themes: vexo
```
``themes/vexo/_config.yml``を設定（SNSとかgithubとか）

### アップデートもできる
```
$ cd theme/vexo
$ git pull
```

### プレビュー（browsersync付）
```
$ cd <Directory>
$ hexo server --draft --open
```
？！ gitmentのcssが露出してた？ので修正、``<%-　%>``で包み忘れ？  
themes/vexo/layout/_partial/head.ejs:25
```
        <%- css('css/plugins/gitment.css') %>
```

きれいなテーマ！

## 感想
- Hexoシンプルでいい!
- もっさりまではいかないけどもパパッとした表示速度ではない、もう少し機敏さほしい
- どこかにデプロイしてみよう
- 次はliquidでテーマつくってみよう


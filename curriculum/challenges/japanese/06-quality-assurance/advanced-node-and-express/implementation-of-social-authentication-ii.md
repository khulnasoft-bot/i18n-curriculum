---
id: 589a69f5f9fc0f352b528e71
title: ソーシャル認証の実装Ⅱ
challengeType: 2
forumTopicId: 301557
dashedName: implementation-of-social-authentication-ii
---

# --description--

GitHub 認証の最後の設定作業として、ストラテジーそのものを作成します。 `passport-github@~1.1.0` has already been added as a dependency, so require it in your `auth.js` file as `GitHubStrategy` like this: `const GitHubStrategy = require('passport-github').Strategy;`. 環境変数を使用できるように、`dotenv` の require と設定を忘れないでください。

GitHub ストラテジーを設定するには、インスタンス化された `GitHubStrategy` を使用するよう Passport に指示する必要があります。これは 2 つの引数を受け取ります。1 つはオブジェクト (`clientID`、`clientSecret` および `callbackURL` を含む) で、もう 1 つはユーザーが正常に認証されたときに呼び出される関数です。この関数は、ユーザーが新規かどうかを判断し、ユーザーのデータベースオブジェクトに最初にどのフィールドを保存するかを決めます。 この手順は多くのストラテジーで一般的ですが、特定のストラテジーの GitHub README に概説されているように、より多くの情報が必要な場合もあります。 たとえば、Google では*スコープ*も必要です。スコープは、リクエストがどのような種類の情報を返すよう求めているのかを判断し、そのようなアクセスを承認するようユーザーに求めます。

The current strategy you are implementing authenticates users using a GitHub account and OAuth 2.0 tokens. アプリケーションの作成時に取得したクライアント ID とシークレットは、ストラテジーの作成時にオプションとして提供されます。 ストラテジーには、アクセストークンとオプションの更新トークンを受け取る `verify` コールバックや、認証されたユーザーの GitHub プロファイルを含む `profile` も必要です。 `verify` コールバックでは、ユーザーを提供する `cb` を呼び出して認証を完了する必要があります。

新しいストラテジーは次のようになります。

```js
passport.use(new GitHubStrategy({
  clientID: process.env.GITHUB_CLIENT_ID,
  clientSecret: process.env.GITHUB_CLIENT_SECRET,
  callbackURL: /*INSERT CALLBACK URL ENTERED INTO GITHUB HERE*/
},
  function(accessToken, refreshToken, profile, cb) {
    console.log(profile);
    //Database logic here with callback containing your user object
  }
));
```

認証はまだ成功せず、データベースロジックとコールバックがないためエラーになりますが、コンソールに GitHub プロファイルが出力されるはずです！

完成したと思ったら、ページを送信してください。 エラーが発生している場合、<a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#implementation-of-social-authentication-ii-4" target="_blank" rel="noopener noreferrer nofollow">この時点までの完成形のコードをこちらで確認できます</a>。

# --hints--

`passport-github` dependency should be added.

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'passport-github',
    'Your project should list "passport-github" as a dependency'
  );
}
```

`passport-github` should be required.

```js
async () => {
  const url = new URL("/_api/auth.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /require.*("|')passport-github("|')/gi,
    'You should have required passport-github'
  );
}
```

GitHub ストラテジーをここまで正しく設定する必要があります。

```js
async () => {
  const url = new URL("/_api/auth.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /passport\.use.*new GitHubStrategy/gis,
    'Passport should use a new GitHubStrategy'
  );
  assert.match(
    data,
    /callbackURL:\s*("|').*("|')/gi,
    'You should have a callbackURL'
  );
  assert.match(
    data,
    /process\.env(\.GITHUB_CLIENT_SECRET|\[(?<q>"|')GITHUB_CLIENT_SECRET\k<q>\])/g,
    'You should use process.env.GITHUB_CLIENT_SECRET'
  );
  assert.match(
    data,
    /process\.env(\.GITHUB_CLIENT_ID|\[(?<q>"|')GITHUB_CLIENT_ID\k<q>\])/g,
    'You should use process.env.GITHUB_CLIENT_ID'
  );
}
```

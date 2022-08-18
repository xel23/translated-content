---
title: Application Context (アプリケーションコンテキスト)
slug: Glossary/application_context
tags:
  - CodingScripting
  - Glossary
translation_of: Glossary/application_context
---
**アプリケーションコンテキスト**は、それに適用される[マニフェスト](/ja/docs/Web/Manifest)のある最上位の{{Glossary("Browsing_context", "閲覧コンテキスト")}}です。

アプリケーションコンテキストが、ユーザーエージェントが深いリンクに移動することを要求された結果として生成された場合、ユーザーエージェントがユーザーエージェントはすぐに置換が有効となった深いリンクに移動しなければなりません。そうでないと、アプリケーションコンテキストが生成された時に、ユーザーエージェントは、すぐに置換が有効となった開始 URL に移動しないといけなくなります

なお、開始 URL は start_url メンバーの値である必要はありません。ユーザーやユーザーエージェントは、アプリケーションがホーム画面に追加されたりブックマークされたりしたときに、これを変更することがあります。
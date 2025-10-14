# リンク・ナビゲーション系のタグ
HTML5で定義されているタグは100種類以上あり、`<body>`内で使えるタグは約90種類である。この中から実務でよく使うタグを次のように分類し、タグの性質と使い方をまとめていく。今回は、**リンク・ナビゲーション系**のタグをまとめる。
|分類|主なタグ|用途|
|-------------|------------------------------|---------------|
|[**構造・セクション系**](structure.md)|`<header>`,`<main>`,`<footer>`,`section>`,`<article>`,`<aside>`,`<nav>`,`<div>`|ページ構造を作る|
|[**テキスト系**](text.md)|`<h1>`~`<h6>`,`<p>`,`<span>`,`<strong>`,`<em>`,`<br>`,`<hr>`,`<blockquote>`,`<code>`|文章や文字装飾|
|**メディア系**|`<img>`,`<picture>`,`<audio>`,`<video>`,`<canvas>`,`<svg>`|画像・動画・音声など|
|**リンク・ナビゲーション系**|`<a>`,`<button>`,`<ul>`,`<ol>`,`<li>`|リンクやメニュー|
|**フォーム・入力系**|`<form>`,`<input>`,`<textarea>`,`<select>`,`<option>`,`<label>`|入力フォーム関連|
|**スクリプト・組み込み系**|`<script>`,`<noscript>`,`<template>`|JSなどの埋め込み|
|**その他**|`<details>`,`<summary>`,`<table>`,`<tr>`,`<td>`,`<figure>`,`<figcaption>`|補助的な情報や表など|

## `<a>`タグ
## `<button>`タグ
`<button>`タグは、HTMLで**ユーザーがクリックできるボタン**を作るためのタグです。次のように設置します。
1.`<button id="exampleButtton">ボタン</button>`を設置  
2.JavaScriptファイルでidからボタンを認識し、クリックを監視して処理を書く  
```javascript
const Button=document.getElementById("exampleButton");
Button.addEventListener('click',()=>{
//ここに処理書く
})
```



#buttonの使い方  
1.`<button id="exampleButtton">ボタン</button>`を設置  
2.JavaScriptファイルでidからボタンを認識し、クリックを監視して処理を書く  
```javascript
const Button=document.getElementById("exampleButton");
Button.addEventListener('click',()=>{
//ここに処理書く
}
```

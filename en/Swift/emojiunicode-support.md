You can use any unicode character (including emoji) as variable names or in Strings.

```js
  var 😄 = "Smiley"                                 
  println(😄) // will print "Smiley"
  let 🌍 = "🐶🐺🐱🐭"
  var 🚢: String[] = []
  for 💕 in 🌍 {
      🚢.append(💕+💕)
  }
  println(🚢) // will print [🐶🐶, 🐺🐺, 🐱🐱, 🐭🐭]
```

**Which, in Xcode looks like**

<img src="http://mhm5000.gitbooks.io/swift-cheat-sheet/content/img/swift-emoji.png" alt="Swift Emoji" width="400px">

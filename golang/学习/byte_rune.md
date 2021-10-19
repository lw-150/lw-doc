# byte与rune类型

1. uint8类型，或者叫 byte 型，代表了ASCII码的一个字符。
2. rune类型，代表一个 UTF-8字符。
3. 当需要处理中文、日文或者其他复合字符时，则需要用到rune类型
## 例子：
```
func changeString() {
    s1 := "a中国b1北京2"
    // 强制类型转换
    byteS1 := []byte(s1)
    byteS1[0] = 'H'
    fmt.Println(string(byteS1))

    s2 := "1北京2a中国b"
    runeS2 := []rune(s2)
    runeS2[0] = '狗'
    fmt.Println(string(runeS2))
}
```
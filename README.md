# 如何優雅地在小狼毫使用倉頡輸人法

## 使用方法

用data文件夾中的文件替換掉小狼毫程序文件夾下data文件夾中的同名文件即可。

教學影片（YouTube）：https://youtu.be/ExTGG1JV76g

教學影片（Bilibili）：https://www.bilibili.com/video/bv1JK411L72X

## 修改版與原版的不同

### 1 候選詞順序固定

在原版小狼毫自帶的倉頡輸入法中，在你輸入重碼字詞時，它會將你當用的字詞向前排。而在修改後的這個版本中，候選詞的順序被固定了。

### 2 候選字順序修正

在倉頡輸入法中，候選字的順序是很重要的，因為你在重碼字的編碼前按下「難」鍵，輸入時便可以直接輸入第二個候選字。比如，你在按下「廿田」時會出現的前兩個候選字為「苗」和「曲」，而你在按下「難廿田」時出現的第一個候選字為「曲」。不過，原版小狼毫自帶的倉頡輸入法破壞了這個規則。而在修改後的這個版本中，這個規則又被修復了。

### 3 詞語輸入模式修正

比方說，在原版的小狼毫倉頡輸入一個二字詞語時，需要輸入需要按下它的第一個字首碼、第一個字尾碼、第二個字首碼、第二個字次首碼和第二個字尾碼。例回，輸入「陳清」這個詞語需要按下「弓田水手月」。而在修改後，你需要按下這個詞語的所有字的全碼。例回，輸入「陳清」這個詞語需要按下「弓中木田水手一月」。

### 4 標點符號輸入

在這個版本中，我修改了輸入部分標點時的候選項。比如按「]」鍵時，在原本的版本中，會出現「」】〕］ 」四個標點供用戶選擇，而在修改後的版本中，會先後兩次分別輸出「「」和「」」。

### 5 詞庫用字

在原版的小狼毫中，默認詞庫更喜歡用「爲」字而不是「為」字，更喜歡用「啓」字而不是「啟」字，而「著」和「着」二字的用法也做了區分。而在修改後的版本中，這些異體字都被收錄了進來。

如果你不喜歡這個版本的用字習慣，你可以在data\essay.txt文件中修改你喜歡的用字。

## 目前己經暴露出來的問題及補救方法

### 1 有些詞打不出來

比如說，你在用修改後的版本打字時，「有很多」這個詞是打出不來的。你在打「有很多」輸入法會自動補充一個「人」字在後面。

這個問題已在20200508被完美解決。方法是：在cangjie5.schema.yaml文件中engine\translators中加入一個script_translator，並將engine\filters中的uniquifier放在最後（否則會出現候選詞重複出現的問題）。

### 2 候選詞順序問題

比如說，你在打「劇本」這個詞時，你按下「卜人中弓木一」後候選詞「刻本」永遠排在「劇本」前面。而且在輸入「劇本作者」這種由兩個詞組成的長詞時，其默認輸出一直是「刻本作者」。

## 更新日誌

注：日期格式為yymmdd，20200404以前的都沒有記

20200404 更新了essay.txt中帶有「溼/濕」和「痴/癡」的詞。現在「溼/濕」和「痴/癡」二字的兩種寫法都帶有提示詞了。

20200508 更新了cangjie5.schema.yaml文件，完美地解決了有些詞打不出來的問題。

20200514 更新了essay.txt中帶有「着/著」、「為/爲」和「偽/僞」的詞。現在「着/著」、「為/爲」和「偽/僞」三字的兩種寫法都帶有提示詞了。

20200612 更新了cangjie5.dict.yaml。現在字典中有80000多字了。

20200703 更新了essay.txt中帶有「絕/絶」的詞。現在「痴/癡」字的兩種寫法都帶有提示詞了。

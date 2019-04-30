
+++
title = "Python Basic oop No.1"

# View.
#   1 = List
#   2 = Compact
#   3 = Card
view = 3
+++


python使用物件導向程式設計，  
起手式，利用class關鍵字宣告(描述)你的物件，  
物件會有名稱(class name)、特徵 (attributes)、還有行為 methods，  
以下列程式碼來看，People是物件的名稱，name & phone 是特徵，  
print_profile是你給予這個物的動作，進而得到你想要的結果。  

```python

class People ():
    def __init__(self, name, phone):
        repr('self. =>代表賦值')
        self.name = name
        self.phone = phone

    def print_profile(self):
        print(self.name, self.phone)


people = People('Jimmy', '1234567')

people.print_profile()

```

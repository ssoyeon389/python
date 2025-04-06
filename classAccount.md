import random

class Account:
    account_count = 0
    def __init__(self, name, balance):
        self.name = name
        self.balance = balance
        self.bank = "SC은행"
        self.count = 0
        num1 = random.randint(0, 999)
        num2 = random.randint(0, 99)
        num3 = random.randint(0, 999999)

        num1 = str(num1).zfill(3)
        num2 = str(num2).zfill(2)
        num3 = str(num3).zfill(6)
        self.account_number = num1 + '-' + num2 + '-' + num3
        Account.account_count += 1

    def get_account_num(cls):
        print(cls.account_count)

    def deposit(self, amount):
        if amount >=1:
            self.balance += amount
            self.count += 1
            if self.count % 5 == 0:
                self.balance += self.balance * (1/100)
            
    def withdraw(self, amount):
        if self.balance >= amount:
            self.balance -= amount
        else:
            print("잔액 부족")
    def display_info(self):
        print("은행 이름:" + self.bank)
        print("예금주:" + self.name)
        print("계좌번호:", self.account_count)
        print("잔고:{}원".format(self.balance))

kim = Account("김민수", 100)
Lee = Account("이민수", 100)
print(kim.balance)
for i in range(0, 5+1):
    kim.deposit(1)
kim.display_info()

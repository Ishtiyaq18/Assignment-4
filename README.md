# Assignment-4

#1.1 Write a Python Program(with class concepts) to find the area of the triangle using the below formula.
#area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
#Function to take the length of the sides of triangle from user should be defined in the parent
#class and function to calculate the area should be defined in subclass.

class Shape:
    def __init__(self, a,b,c):
        self.a = a
        self.b = b
        self.c = c
        self.sides=[]    
    def setsides(self):
        self.sides = [self.a,self.b,self.c]
        return self.sides    
class Triangle(Shape):
    def __init__(self,a,b,c):
        Shape.__init__(self,a,b,c)
        super(Triangle,self).__init__(a,b,c)
    def findArea(self):
        # calculate the semi-perimeter
        s = (self.a+self.b+self.c)/2
        area = (s*(s-self.a)*(s-self.b)*(s-self.c)) ** 0.5
        try:
            print('The area of the triangle is %0.2f' %area)    
        except:
                print('Incorrect entry - Not a Triangle when one side is bigger than the other two combined')            

t = Triangle(1,11,2)
t.findArea()

#1.2 Write a function filter_long_words() that takes a list of words and an integer n and returns
#the list of words that are longer than n.

def wordlen(list):
    print('Type an integer')
    num=int(input())
    print('Words greater than integer:')
    for n in list:
        if (len(n))>num:
            print(n)
        
list=['tiger','lion','cheetah']
wordlen(list)

# 2.1 Write a Python program using function concept that maps list of words into a list of integers
# representing the lengths of the corresponding words .
def cntltrs():
    print('Type words seperated by comma')
    list=[]
    length=[]
    words=input()
    list.append(words.split(','))
    for l in list:
        for i in l:
            length.append(len(i))
        print(length)

cntltrs()

# 2.2 Write a Python function which takes a character (i.e. a string of length 1) and returns True if
# it is a vowel, False otherwise.

def identifyletter():
    print('Please type a letter')
    string=input()
    vowels='a','e','i','o','u'
    print("Is this letter a vowel?")
    for v in vowels:
        if v==string:
            print(True)
            break
    else:
        print(False)
    
identifyletter()

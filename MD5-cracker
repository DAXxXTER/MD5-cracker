#!/usr/bin/python
# This script uses a bruteforce method to crack MD5 hashes
# If the password length is longer than ~10 characters, it could take a considerable time to crack
# Also, this code can be very CPU intensive if you are running it for long periods of time
# or running several instances at once. Be kind to it, it just a proof of concept.
 
import itertools
import sys
import hashlib
import time
 
lower = 'abcdefghijklmnopqrstuvwxyz'
upper = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
lowup = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
numbers = '1234567890'
lownum = 'abcdefghijklmnopqrstuvwxyz1234567890'
upnum = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890'
all = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()-_+=~`[]{}|\:;"'
 
def brutecrack():
        length = int(sys.argv[2]) + 1
 
        if sys.argv[1] == '-l':
                final = lower
        elif sys.argv[1] == '-U':
                final = upper
        elif sys.argv[1] == '-n':
                final = numbers
        elif sys.argv[1] == '-aA':
                final = lowup
        elif sys.argv[1] == '-ln':
                final = lownum
        elif sys.argv[1] == '-Un':
                final = upnum
        elif sys.argv[1] == '-s':
                final = all
 
        for i in range(1,length):
                for p in itertools.product(final, repeat=i):
                        crack = ''.join(p)
                        m = hashlib.md5()
                        m.update(crack)
                        if m.hexdigest() != sys.argv[3]:
                                print "[-] scan otomatis dan Mencoba segala kemungkinan   => ",crack
                                
                                
                        else:
                                print "[+] password berhasil di crack   => ", crack
                                sys.exit()
 
def main():
        if len(sys.argv) <=1:
                print '''\n
-----------------------------------------
| DAXxXTER MD5-Crack v1.2               | trimakasih kepada tuhan yesus kristus
| ceded by : rio suyanto                |     karna memberikan saya hikmat
| email    : rio_suyanto00@yahoo.co.id  |        kekuatan dan kesehatan
| blog     : rio-suyanto.blogspot.com   |
-----------------------------------------      Semoga ini dapat membantu.
________________________________________________________________________________
\n
Cara pake : python DAXxXTERcrack.py (pilihan) (jumlah karakter) (hase md5)
Contoh	  : python DAXxXTERcrack.py -s 10 d5ed38fdbf28bc4e58be142cf5a17cf5

-l   | [abcdefghijklmnopqrstuvwxyz]
-U   | [ABCDEFGHIJKLMNOPQRSTUVWXYZ]
-n   | [1234567890]
-ln  | [abcdefghijklmnopqrstuvwxyz1234567890]
-Un  | [ABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890]
-s   | [-l] + [-U] + [-n] + !@#$%^&*()-_+=~`[]{}|\:;"]\n'''

                sys.exit(1)
        else:
                brutecrack()
 
if __name__ == "__main__" :
        main()

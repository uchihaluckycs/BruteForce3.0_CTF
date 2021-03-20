# BruteForce3.0 CTF 

## z3-ti challenge

### After decompiling and analyzing the binary file
###### 1. According to given binary file, we need to pass an argument that is password which is 11 digit long
###### 2. After passing an argument, the binary file perform some calculations and check some conditions on given argument
###### 3. If the argument satisfies those conditions then we get the flag

### Task : Find the 11 digit password
##### Copy the decompiled code and convert it to python
![cutter](https://user-images.githubusercontent.com/32408501/111876790-61aa1b00-89c6-11eb-9c68-093948f1432f.png)
![cutter](https://user-images.githubusercontent.com/32408501/111876809-72f32780-89c6-11eb-9f4c-83d1d91e329e.png)
```
# pip3 install z3-solver
from z3 import *

# consider m40,m60,m64,m68,m6c,m70,m74,m78,m7c,m80,m84,m88 are memory locations and initially zero
m40 = 0
m60 = 0
m80 = 0
m84 = 0
m74 = 0
m7c = 0
m78 = 0
m88 = 0
m6c = 0
m70 = 0
m68 = 0
m64 = 0

# consider p0 to p10 are 11 variables where each variable represents one char in 11 digit password
# We need p0 to p10 values but we don't know what are those values
# Assign p0 to p10 as BitVec
p0 = BitVec("p0",8)
p1 = BitVec("p1",8)
p2 = BitVec("p2",8)
p3 = BitVec("p3",8)
p4 = BitVec("p4",8)
p5 = BitVec("p5",8)
p6 = BitVec("p6",8)
p7 = BitVec("p7",8)
p8 = BitVec("p8",8)
p9 = BitVec("p9",8)
p10 = BitVec("p10",8)

# converted decompiled code to python
eax = m40
rsi = p8
eax += 0x25
m40 = eax
eax = p4
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 7
m40 = eax
ecx = m40
eax = p1
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 0x14
m40 = eax
eax = p8
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax -= 0x25
m40 = eax
eax = p6
ecx = m40
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 1
m40 = eax
eax = p9
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax -= 3
m40 = eax
ecx = m40
eax = p4
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 0x27
m40 = eax
eax = p7
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 5
m40 = eax
eax = p4
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax -= 0x15
m40 = eax
eax = p10
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 3
m40 = eax
ecx = m40
eax = p2
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax += 0x10
m40 = eax
ecx = m40
edx = m60
eax = p2
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 0xd
m40 = eax
eax = p9
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 0xd
m40 = eax
eax = p5
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 7
m40 = eax
eax = p7
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 0xb
m40 = eax
eax = p8
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax += 3
m40 = eax
eax = p7
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 0xa
m40 = eax
ecx = m40
eax = p0
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 4
m40 = eax
eax = p7
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax += 6
m40 = eax
eax = p5
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 0x19
m40 = eax
ecx = m40
eax = p3
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 8
m40 = eax
eax = p10
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax += 0xf
m40 = eax
ecx = m40
eax = p9
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax -= 0xe
m40 = eax
eax = p10
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 0x1a
m40 = eax
eax = p7
ecx = m40
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 0x1d
m40 = eax
ecx = m40
eax = p1
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 8
m40 = eax
ecx = m40
eax = p2
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 1
m40 = eax
eax = m60
eax -= 0x8082
m60 = eax
eax = m40
eax += 0x14
m40 = eax
eax = p8
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 0x1a
m40 = eax
eax = p10
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax += 0x16
m40 = eax
eax = p9
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax -= 9
m40 = eax
eax = p10
ecx = m40
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 0x1b
m40 = eax
ecx = m40
eax = p0
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 0x11
m40 = eax
eax = m70
eax -= 0x6a3a
m70 = eax
eax = m40
eax -= 0xb
m40 = eax
eax = p7
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 0x17
m40 = eax
ecx = m40
eax = p0
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax -= 0x11
m40 = eax
eax = m74
eax -= 0x60e0
m74 = eax
eax = m40
eax -= 0xc
m40 = eax
ecx = m40
eax = p1
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 8
m40 = eax
ecx = m40
eax = p3
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
m40 = eax
ecx = m40
eax = p5
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 0x16
m40 = eax
eax = p5
ecx = m40
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 4
m40 = eax
ecx = m40
eax = p0
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax -= 9
m40 = eax
eax = p10
ecx = m40
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 0x17
m40 = eax
eax = m6c
eax -= 0x7b17
m6c = eax
eax = m40
eax += 0x23
m40 = eax
ecx = m40
eax = p3
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 7
m40 = eax
ecx = m40
eax = p3
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax -= 0x16
m40 = eax
eax = p10
edx = m40
ecx = m60
edx *= eax
edx += ecx
m60 = edx
edx = m40
edx += 0xb
m40 = edx
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 2
m40 = eax
eax = m78
eax -= 0x7eef
m78 = eax
eax = m40
eax += 0x14
m40 = eax
ecx = m40
eax = p0
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 1
m40 = eax
ecx = m40
eax = p0
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 0x19
m40 = eax
eax = p10
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 0x21
m40 = eax
eax = p5
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax -= 5
m40 = eax
eax = p8
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax -= 0x22
m40 = eax
eax = p9
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0xd
m40 = eax
ecx = m40
eax = p1
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax -= 0x10
m40 = eax
ecx = m40
eax = p3
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax += 0x21
m40 = eax
ecx = m40
eax = p1
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 0x18
m40 = eax
eax = m84
eax -= 0x5e1d
m84 = eax
eax = m40
eax += 0x1b
m40 = eax
ecx = m40
eax = p0
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 6
m40 = eax
eax = p7
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 0x1c
m40 = eax
eax = p6
ecx = m40
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 4
m40 = eax
eax = p8
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 0xd
m40 = eax
eax = m80
eax -= 0x62a4
m80 = eax
eax = m40
eax -= 2
m40 = eax
eax = p7
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 0x18
m40 = eax
eax = p4
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax -= 2
m40 = eax
ecx = m40
eax = p2
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 0x17
m40 = eax
ecx = m40
edx = m74
eax = p2
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax -= 3
m40 = eax
eax = p4
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 0xa
m40 = eax
eax = p4
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax += 0xe
m40 = eax
eax = p5
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 0x17
m40 = eax
eax = p5
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 0xf
m40 = eax
eax = p6
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax -= 0x10
m40 = eax
eax = p8
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0xc
m40 = eax
eax = p6
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax -= 0x13
m40 = eax
ecx = m40
eax = p2
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 0x19
m40 = eax
ecx = m40
eax = p2
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 0x13
m40 = eax
ecx = m40
eax = p2
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0x13
m40 = eax
ecx = m40
eax = p10
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax -= 0xb
m40 = eax
ecx = m40
eax = p1
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 0x1e
m40 = eax
ecx = m40
eax = p2
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax -= 7
m40 = eax
ecx = m40
eax = p3
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 9
m40 = eax
eax = p6
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax -= 0x1d
m40 = eax
ecx = m40
edx = m70
eax = p9
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax += 7
m40 = eax
ecx = m40
eax = p1
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 0x21
m40 = eax
eax = p5
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 5
m40 = eax
ecx = m40
eax = p1
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 2
m40 = eax
ecx = m40
eax = p2
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 0x18
m40 = eax
eax = p8
ecx = m40
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 1
m40 = eax
eax = p6
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0x25
m40 = eax
eax = p4
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 1
m40 = eax
eax = p6
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 0x1c
m40 = eax
eax = p4
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax -= 9
m40 = eax
eax = p6
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax += 0xd
m40 = eax
ecx = m40
eax = p3
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 3
m40 = eax
eax = m68
eax -= 0x59d7
m68 = eax
eax = m40
eax -= 0x10
m40 = eax
eax = p6
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax += 0x2b
m40 = eax
eax = p8
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 0xf
m40 = eax
eax = p8
ecx = m40
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax -= 2
m40 = eax
eax = p6
ecx = m40
edx = m60
eax *= ecx
eax += edx
m60 = eax
eax = m40
eax -= 7
m40 = eax
ecx = m40
eax = p3
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax += 0x18
m40 = eax
eax = m64
eax -= 0x5919
m64 = eax
eax = m40
eax -= 0x1a
m40 = eax
eax = m7c
eax -= 0x8c42
m7c = eax
eax = m40
eax -= 0xf
m40 = eax
ecx = m40
eax = p1
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax += 0xb
m40 = eax
eax = p4
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 0x17
m40 = eax
ecx = m40
eax = p3
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax -= 0x21
m40 = eax
eax = p5
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0x11
m40 = eax
eax = p7
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 9
m40 = eax
ecx = m40
eax = p1
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax -= 4
m40 = eax
eax = m88
eax -= 0x4dbc
m88 = eax
eax = m40
eax -= 0x18
m40 = eax
ecx = m40
eax = p0
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 7
m40 = eax
ecx = m40
edx = m68
eax = p3
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 0x1a
m40 = eax
eax = p5
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 0xa
m40 = eax
eax = p4
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax += 0x11
m40 = eax
ecx = m40
eax = p0
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 0x26
m40 = eax
eax = p6
ecx = m40
edx = m84
eax *= ecx
eax += edx
m84 = eax
eax = m40
eax += 0x24
m40 = eax
eax = p8
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 0x14
m40 = eax
eax = p7
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0x13
m40 = eax
eax = p9
ecx = m40
edx = m88
eax *= ecx
eax += edx
m88 = eax
eax = m40
eax -= 0x1a
m40 = eax
ecx = m40
eax = p0
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax += 0x20
m40 = eax
eax = p9
ecx = m40
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax -= 0xe
m40 = eax
eax = p9
ecx = m40
edx = m6c
eax *= ecx
eax += edx
m6c = eax
eax = m40
eax -= 7
m40 = eax
ecx = m40
eax = p4
edx = m70
eax *= ecx
eax += edx
m70 = eax
eax = m40
eax -= 0xd
m40 = eax
ecx = m40
eax = p1
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax -= 6
m40 = eax
eax = p9
ecx = m40
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax += 0x10
m40 = eax
ecx = m40
eax = p2
edx = m68
eax *= ecx
eax += edx
m68 = eax
eax = m40
eax -= 5
m40 = eax
eax = p9
ecx = m40
edx = m78
eax *= ecx
eax += edx
m78 = eax
eax = m40
eax += 0xa
m40 = eax
ecx = m40
edx = m64
eax = p3
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax += 0x12
m40 = eax
eax = p10
ecx = m40
edx = m64
eax *= ecx
eax += edx
m64 = eax
eax = m40
eax -= 0x22
m40 = eax
eax = p5
ecx = m40
edx = m74
eax *= ecx
eax += edx
m74 = eax
eax = m40
eax += 9
m40 = eax
eax = p7
ecx = m40
edx = m80
eax *= ecx
eax += edx
m80 = eax
eax = m40
eax -= 4
m40 = eax
ecx = m40
eax = p0
edx = m7c
eax *= ecx
eax += edx
m7c = eax
eax = m40
eax += 0x17
m40 = eax
eax = p8
ecx = m40
edx = m68
eax *= ecx
eax += edx
m68 = eax

s = Solver()
# Adding rules begin
s.add(m60 == 0)
s.add(m80 == 0)
s.add(m84 == 0)
s.add(m74 == 0)
s.add(m7c == 0)
s.add(m78 == 0)
s.add(m88 == 0)
s.add(m6c == 0)
s.add(m70 == 0)
s.add(m68 == 0)
s.add(m64 == 0)
# p0 to p10 char printable range is 32 to 127 in decimal
s.add(p0 >= 32, p0 <= 127) 
s.add(p1 >= 32, p1 <= 127)
s.add(p2 >= 32, p2 <= 127)
s.add(p3 >= 32, p3 <= 127)
s.add(p4 >= 32, p4 <= 127)
s.add(p5 >= 32, p5 <= 127)
s.add(p6 >= 32, p6 <= 127)
s.add(p7 >= 32, p7 <= 127)
s.add(p8 >= 32, p8 <= 127)
s.add(p9 >= 32, p9 <= 127)
s.add(p10 >= 32, p10 <= 127)
# Adding rules end
s.check()
res = s.model()
print(chr(res[p0].as_long())+chr(res[p1].as_long())+chr(res[p2].as_long())+chr(res[p3].as_long())+chr(res[p4].as_long())+chr(res[p5].as_long())+chr(res[p6].as_long())+chr(res[p7].as_long())+chr(res[p8].as_long())+chr(res[p9].as_long())+chr(res[p10].as_long()))
```


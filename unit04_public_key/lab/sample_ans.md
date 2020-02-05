
Try not to look at these answers, unless you really have too ..

## A.2
```python
import rsa
(bob_pub, bob_priv) = rsa.newkeys(512)
print bob_pub
print bob_priv
ciphertext = rsa.encrypt('Here is my message', bob_pub)
message = rsa.decrypt(ciphertext, bob_priv)
print(message.decode('utf8'))
```

A sample run gives:

<pre>
PublicKey(7044152640361902500168576401792350494310726185372977704588682647070501920385795486653093710793158373161949147824992313215786223524754692116109993477603703, 
65537)
PrivateKey(7044152640361902500168576401792350494310726185372977704588682647070501920385795486653093710793158373161949147824992313215786223524754692116109993477603703, 
65537, 1031520101462581111343482730793310461173078401529280666355457029829494893917496934907266419334856470211959662572029962392609614789178286814805200163248601, 
7009636621105341733056641551350073875772161289792261672243040042003271353299512989, 1004924081107519375914073833480034561474534624800691686376057520755477027)
Here is my message
</pre>
The keys are (e,N) for the public key, and (d,N) for the private key. In this case the value of N is:
<pre>
7044152640361902500168576401792350494310726185372977704588682647070501920385795486653093710793158373161949147824992313215786223524754692116109993477603703
</pre>
And e is:
<pre>
65537
</pre>
For the decryption key, N is the same value as the encryption key, and d is:
<pre>
1031520101462581111343482730793310461173078401529280666355457029829494893917496934907266419334856470211959662572029962392609614789178286814805200163248601
</pre>
The two prime numbers used (p and q) are then:
<pre>
7009636621105341733056641551350073875772161289792261672243040042003271353299512989 1004924081107519375914073833480034561474534624800691686376057520755477027
</pre>
Sample:
<pre>
>>> 7009636621105341733056641551350073875772161289792261672243040042003271353299512989*1004924081107519375914073833480034561474534624800691686376057520755477027 
7044152640361902500168576401792350494310726185372977704588682647070501920385795486653093710793158373161949147824992313215786223524754692116109993477603703L
</pre>
## A.3


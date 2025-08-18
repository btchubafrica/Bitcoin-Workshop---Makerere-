## more into Hashs
sha256 in terminal 


echo -n hello | sha256sum

printf sam->5tomomahmed | sha256sum

```bash
printf '%s' 'somestring' | sha256sum
```

other than this we have loads of hashes :
- `-blake2b512`
- `-blake2s256`
- `-md4`
- `-md5`
- `-md5-sha1`
- `-ripemd`
- `-ripemd160`
- `-rmd160`
- `-sha1`x
- `-sha224`
- `-sha256`
- `-sha3-224`
- `-sha3-256`
- `-sha3-384`
- `-sha3-512`
- `-sha384`
- `-sha512`
- `-sha512-224`
- `-sha512-256`
- `-shake128`
- `-shake256`
- `-sm3`
- `-ssl3-md5`
- `-ssl3-sha1`
- `-whirlpool`



_for nonce in $( seq 100 ) ; do echo "Hello, world! $nonce" | sha256sum ; done_

eth uses keccak256

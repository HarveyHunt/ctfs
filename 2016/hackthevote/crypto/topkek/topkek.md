# TOPKEK

>A CNN reporter had only one question that she couldn't get off her mind

>>Do we even know, who is this 4 CHAN???

>So she set out to find who this 400lb hacker is. During her investigation, she
>came across this cryptic message on some politically incorrect forum online,
>can you figure out what it means?

This challenge presented the following text file:

```
KEK! TOP!! KEK!! TOP!! KEK!! TOP!! KEK! TOP!! KEK!!! TOP!! KEK!!!! TOP!
KEK! TOP!! KEK!! TOP!!! KEK! TOP!!!! KEK! TOP!! KEK! TOP! KEK! TOP! KEK! TOP!
KEK!!!! TOP!! KEK!!!!! TOP!! KEK! TOP!!!! KEK!! TOP!! KEK!!!!! TOP!! KEK!
TOP!!!! KEK!! TOP!! KEK!!!!! TOP!! KEK! TOP!!!! KEK!! TOP!! KEK!!!!! TOP!! KEK!
TOP!!!! KEK!! TOP!! KEK!!!!! TOP! KEK! TOP! KEK!!!!! TOP! KEK! TOP!!!!! KEK!
TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP!
KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK!! TOP!! KEK!!! TOP! KEK! TOP!! KEK!
TOP!! KEK! TOP! KEK! TOP! KEK! TOP!!!!! KEK! TOP!! KEK! TOP! KEK!!!!! TOP!!
KEK! TOP! KEK!!! TOP! KEK! TOP! KEK! TOP!! KEK!!! TOP!! KEK!!! TOP! KEK! TOP!!
KEK! TOP!!! KEK!! TOP! KEK!!! TOP!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP! KEK!!!
TOP!! KEK!! TOP!!! KEK! TOP! KEK! TOP! KEK! TOP! KEK!! TOP!!! KEK!! TOP! KEK!
TOP!!!!! KEK! TOP!!! KEK!! TOP! KEK!!! TOP!! KEK!!! TOP! KEK! TOP!! KEK!!
TOP!!! KEK! TOP! KEK!! TOP! KEK!!!! TOP!!! KEK! TOP! KEK!!! TOP! KEK! TOP!!!!!
KEK! TOP!! KEK! TOP!!! KEK!!! TOP!! KEK!!!!! TOP! KEK! TOP! KEK! TOP!!! KEK!
TOP! KEK! TOP!!!!! KEK!! TOP!! KEK! TOP! KEK!!! TOP! KEK! TOP! KEK!! TOP!
KEK!!! TOP!! KEK!! TOP!! KEK! TOP! KEK! TOP!!!!! KEK! TOP!!!! KEK!! TOP! KEK!!
TOP!! KEK!!!!! TOP!!! KEK! TOP! KEK! TOP! KEK! TOP! KEK! TOP!!!!! KEK! TOP!!
KEK! TOP! KEK!!!!! TOP!! KEK! TOP! KEK!!! TOP!!! KEK! TOP!! KEK!!! TOP!! KEK!!!
TOP! KEK! TOP!! KEK! TOP!!! KEK!! TOP!! KEK!! TOP!!! KEK! TOP! KEK! TOP!!!!!
KEK! TOP!! KEK!! TOP!! KEK!! TOP!!! KEK! TOP! KEK! TOP! KEK! TOP!! KEK! TOP!!!
KEK!! TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK!
TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP! KEK! TOP!!!!! KEK! TOP!
KEK!! TOP! KEK! TOP!! KEK!! TOP!! KEK!! TOP!! KEK! TOP! KEK!! TOP! KEK! TOP!!
KEK!! TOP! KEK!!!! TOP! KEK!! TOP! KEK!!!! TOP! KEK!! TOP! KEK!!!! TOP! KEK!
TOP!!!!! KEK! TOP!
```

As only the only words in the file are TOP and KEK, I assumed that they were to
represent 0 or 1. I thought that the exclamation marks denoted how many times
to repeat 0 or 1. 

With this in mind, I hacked up the following python code:

```python
#!/usr/bin/python3

out = ''

with open('topkek', 'r') as f:
    for w in f.readlines()[0].split():
        if "KEK" in w:
            out += '0' * w.count('!')
        if "TOP" in w:
            out += '1' * w.count('!')

n = int(out, 2)
print('ASCII output: ' + n.to_bytes((n.bit_length() + 7) // 8, 'big').decode())
```

Running this yielded the following output:

```
ASCII output:
flag{T0o0o0o0o0P______1m_h4V1nG_FuN_r1gHt_n0W_4R3_y0u_h4v1ng_fun______K3K!!!}
```

Firing that flag into the site rewarded the team with 50 points. :-)

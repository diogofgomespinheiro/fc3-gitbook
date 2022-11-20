# CMD vs Entrypoint

The `ENTRYPOINT` specifies a command that will always be executed when the container starts.

The `CMD` specifies arguments that will be fed to the `ENTRYPOINT`.

## <mark style="color:purple;">Example:</mark>

```docker
FROM debian:wheezy
ENTRYPOINT ["/bin/ping"]
CMD ["localhost"]
```

Running the image without any argument will ping the localhost:

```bash
$ docker run -it test
PING localhost (127.0.0.1): 48 data bytes
56 bytes from 127.0.0.1: icmp_seq=0 ttl=64 time=0.096 ms
56 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.088 ms
56 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.088 ms
--- localhost ping statistics ---
3 packets transmitted, 3 packets received, 0% packet loss
round-trip min/avg/max/stddev = 0.088/0.091/0.096/0.000 ms
```

Now, running the image with an argument will ping the argument:

```bash
$ docker run -it test google.com
PING google.com (173.194.45.70): 48 data bytes
56 bytes from 173.194.45.70: icmp_seq=0 ttl=55 time=32.583 ms
56 bytes from 173.194.45.70: icmp_seq=2 ttl=55 time=30.327 ms
56 bytes from 173.194.45.70: icmp_seq=4 ttl=55 time=46.379 ms
--- google.com ping statistics ---
5 packets transmitted, 3 packets received, 40% packet loss
round-trip min/avg/max/stddev = 30.327/36.430/46.379/7.095 ms
```



For comparison, if your Dockerfile is:

```docker
FROM debian:wheezy
CMD ["/bin/ping", "localhost"]
```

Running the image without any argument will ping the localhost:

```bash
$ docker run -it test
PING localhost (127.0.0.1): 48 data bytes
56 bytes from 127.0.0.1: icmp_seq=0 ttl=64 time=0.076 ms
56 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.087 ms
56 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.090 ms
--- localhost ping statistics ---
3 packets transmitted, 3 packets received, 0% packet loss
round-trip min/avg/max/stddev = 0.076/0.084/0.090/0.000 ms
```

But running the image with an argument will run the argument:

```bash
docker run -it test bash
root@e8bb7249b843:/#
```

{% hint style="info" %}
Place exec ”$@” at the end of the entrypoint file so it’s possible to run the CMD
{% endhint %}


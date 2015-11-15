# murmur-cvp
Docker image for flaskcvp, a minimal mumble channel viewer protocol server 

Requires an ICE-enabled murmur.

`docker run -d --name=murmur-cvp -p 5000:5000 -e MURMUR_ICE_HOST=murmur -e MURMUR_ICE_PORT=6502 -e MURMUR_CONNECT_URL=mumble://localhost:64738 -e MURMUR_ICESECRETWRITE=mysecret --link murmur:murmur murmur-cvp`

Or with the default values from the Dockerfile:
`docker run -d --name=murmur-cvp -p 5000:5000 --link murmur:murmur murmur-cvp`

Debug mode:
`docker run --name=murmur-cvp -p 5000:5000 --link murmur:murmur -i -t --user root --entrypoint=/bin/bash murmur-cvp`


Server list is available at `http://HOST:5000/`, server channels are viewable at `http://HOST:5000/SERVER_ID`

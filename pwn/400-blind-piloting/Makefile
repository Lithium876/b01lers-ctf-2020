all: blindpiloting

blindpiloting:
	docker build . -t $@
	docker run --name $@ --restart always -itd -p 13306:13306 $@
	docker cp $@:/home/$@/$@ ./$@.dist
	docker cp $@:/lib/x86_64-linux-gnu/libc-2.27.so ./$@.libc
	chmod a+rwx ./$@.dist
	chmod a+rwx ./$@.libc

.PHONY: blindpiloting

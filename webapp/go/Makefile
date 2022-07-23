all: isuports

bench: isuports
	sudo truncate --size 0 /var/log/mysql/slow.log
	sudo truncate --size 0 /var/log/nginx/access.log
	sudo systemctl restart nginx.service
	sudo systemctl restart isuports

alp:
	alp -c alp.yaml ltsv

isuports: go.mod go.sum *.go cmd/isuports/*
	go build -o isuports ./cmd/isuports

test:
	go test -v ./...

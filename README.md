# Nginx as API Gateway Sample

This is a sample project to demonstrate how to use Nginx as API Gateway.

## Prerequisites

- Docker
- Docker Compose

## How to run

```bash
docker-compose -f docker-compose.yml up -d
```

## How to test

You need to add the following line to your `/etc/hosts` file:

```bash
echo "127.0.0.1     api.example.com" >> /etc/hosts
```

Then you can test the API using the following commands:

```bash
curl -Ls http://api.example.com/app01 | grep -i 'application'
curl -Ls http://api.example.com/app02 | grep -i 'application'
curl -Ls http://api.example.com/app03 | grep -i 'application'
```

or

```bash
curl -Ls -o /dev/null -w "%{http_code}\n" http://api.example.com/app01
curl -Ls -o /dev/null -w "%{http_code}\n" http://api.example.com/app02
curl -Ls -o /dev/null -w "%{http_code}\n" http://api.example.com/app03
```

## How to stop

```bash
docker-compose -f docker-compose.yml down
```

## License

MIT License

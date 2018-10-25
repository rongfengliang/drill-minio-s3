# apache drill minio (s3) demo

## How to run

* docker running

```code
docker-compose up -d
```

* config drill s3 storage

just like below, change the key and ip address 

docker-compose s3 both is demoappdemo && server endpoint 
can use http://s3:9000 

```code
{
  "type": "file",
  "connection": "s3a://app/",
  "config": {
    "fs.s3a.access.key": "<key>",
    "fs.s3a.secret.key": "<secret>",
    "fs.s3a.endpoint": "<minio server>",
    "fs.s3a.connection.ssl.enabled": "false", // default isn't  ssl
    "fs.s3a.path.style.access": "true"
  },
  "workspaces": {
    "root": {
      "location": "/",
      "writable": false,
      "defaultInputFormat": null,
      "allowAccessOutsideWorkspace": false
    },
    "tmp": {
      "location": "/tmp",
      "writable": true,
      "defaultInputFormat": null,
      "allowAccessOutsideWorkspace": false
    }
  },
  "formats": {
    "psv": {
      "type": "text",
      "extensions": [
        "tbl"
      ],
      "delimiter": "|"
    },
    "csv": {
      "type": "text",
      "extensions": [
        "csv"
      ],
      "delimiter": ","
    },
    "tsv": {
      "type": "text",
      "extensions": [
        "tsv"
      ],
      "delimiter": "\t"
    },
    "parquet": {
      "type": "parquet"
    },
    "json": {
      "type": "json",
      "extensions": [
        "json"
      ]
    },
    "avro": {
      "type": "avro"
    },
    "sequencefile": {
      "type": "sequencefile",
      "extensions": [
        "seq"
      ]
    },
    "csvh": {
      "type": "text",
      "extensions": [
        "csvh"
      ],
      "extractHeader": true,
      "delimiter": ","
    }
  },
  "enabled": true
}
```
# CRUD

## Create a single document

```json
{
  "id": "1",
  "title": "Welcome to Apache Solr",
  "url": "https://solr.apache.org/",
  "upload_date": "2024-10-30",
  "clicks": 20,
  "tags": ["solr", "documentation"]
}
```

## Get by identifier

```console
http://localhost:8983/solr/test/get?id=1
```

## Search

```console
http://localhost:8983/solr/test/select?q=title:solr
```

## Update

Select command and paste the command:

```json
{
	"id": 1,
	"clicks": {
		"inc": 40
	},
	"tags": {
		"add": [ "intro" ]
	}
}
```

And then retrieve the document:

```console
http://localhost:8983/solr/test/select?q=title:solr
```

## Delete

Switch to `Solr Command` in Solr admin and run:

```console
{
	"delete": {
		"query": "*:*"
	}
}
```

```console
{
	"delete": {
		"id": "1"
	}
}
```
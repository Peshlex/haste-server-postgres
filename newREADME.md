1. I modified package.json to exclude not needed dependancies (redis)

2. I modified config.js to add a PostgreSQL storage type

		"storage": {
			"type": "postgres",
			"connectionUrl": "postgres://haster:secretr@pg:5432/haste_pgdb"
		},

3. I removed the initial Dockerfile and docker-compose.yaml and added my versions.

	- Dockerfile.hastesrv for the haste-server
	- Dockerfile.postgres for the postgresql
	- docker-compose for both haste-server and postgresql

4. I added a schema.sql for startup of postgres with required fields

		create table entries (id serial primary key, key varchar(255) not null, value text not null, expiration int, unique(key));

5. Modified docker-entrypoint.sh in Notepad++ , changed from Windows (CR LF) to Unix (LF) , because it was reading '\r'

6. Added a gist with commands for runnung dockers
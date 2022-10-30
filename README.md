# dbapi
<h1>DB de api blog</h1>
<h2>Grafico entidad de relación<h2>
<img src="https://user-images.githubusercontent.com/32494481/198879996-d0330c0b-d693-4c53-9443-65f55572ada5.png" alt="alt text" title="image Title" />
<h3>Tabla de Usuarios</h3>
CREATE TABLE "User" (
  "id" SERIAL PRIMARY KEY,
  "email" varchar,
  "password" varchar
);
<h3>Tabla de Posts</h3>
CREATE TABLE "Post" (
  "id" SERIAL PRIMARY KEY,
  "user_id" int,
  "tags_id" int,
  "title" varchar,
  "description" varchar,
  "author" varchar,
  "content" text
);
<h3>Tabla de Categorias</h3>
CREATE TABLE "Tags" (
  "id" SERIAL PRIMARY KEY,
  "name" varchar
);
<h3>Tabla de Comentarios</h3>
CREATE TABLE "Comment" (
  "id" SERIAL PRIMARY KEY,
  "post_id" int,
  "comment" varchar
);
<h3>Relaciones</h3>
ALTER TABLE "Post" ADD FOREIGN KEY ("user_id") REFERENCES "User" ("id");

ALTER TABLE "Comment" ADD FOREIGN KEY ("post_id") REFERENCES "Post" ("id");

ALTER TABLE "Post" ADD FOREIGN KEY ("tags_id") REFERENCES "Tags" ("id");


Redwood
=======

Create a new app

	yarn create redwood-app ./redwoodblog

Start to develop

	yarn redwood dev

Install package

	yarn workspace <workspace name> add <package>

## Generation

Generate page

	yarn redwood generate page home /

Generate layout

	yarn redwood generate layout blog

Generate scaffolder

	yarn rw g scaffold post

## Database

Create a migration

	yarn redwood db save create posts

Apply a migration

	yarn rw db up


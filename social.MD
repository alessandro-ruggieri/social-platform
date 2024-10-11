## Database: Social-Platform

# Table: users

- id INT PK AI UNIQUE NOTNULL
- username VARCHAR(60) UNIQUE NOTNULL
- password VARCHAR(60) NOTNULL
- name VARCHAR(60) NOTNULL
- surname VARCHAR(60) NOTNULL
- mail VARCHAR(100) UNIQUE NOTNULL
- phone VARCHAR(20) NULL
- birthday DATE NULL
- sign_date DATE NOTNULL

# Table: posts

- id INT PK AI UNIQUE NOTNULL
- user_id INT FK NOTNULL
- content TEXT NOTNULL
- created DATETIME NOTNULL

# Table: medias

- id INT PK AI UNIQUE NOTNULL
- type ENUM('photo', 'video') NOTNULL
- url VARCHAR(255) NOTNULL UNIQUE

# Table: medias_posts

- media_id INT FK
- post_id INT FK 
- PRIMARY KEY (media_id, post_id)

# Table: tags

- id MEDIUMINT PK AI UNIQUE NOTNULL
- tag_name VARCHAR(255) UNIQUE NOTNULL 

# Table: posts_tags

- post_id INT FK
- tag_id MEDIUMINT FK 
- PRIMARY KEY (post_id, tag_id)

# Table: likes

- id BIGINT PK AI UNIQUE NOTNULL
- post_id INT FK
- user_id INT FK 
- UNIQUE (post_id, user_id)

# Table: comments

- id BIGINT PK AI UNIQUE NOTNULL
- post_id INT FK
- user_id INT FK 
- content TEXT NOTNULL
- created DATETIME NOTNULL
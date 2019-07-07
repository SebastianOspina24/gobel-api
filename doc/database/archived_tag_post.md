# archived_tag_post

## Description

<details>
<summary><strong>Table Definition</strong></summary>

```sql
CREATE TABLE `archived_tag_post` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  `tag_id` int(11) unsigned NOT NULL,
  `archived_post_id` int(11) unsigned NOT NULL,
  `created_at` datetime DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `updated_at` datetime DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `tag_id` (`tag_id`),
  KEY `archived_post_id` (`archived_post_id`),
  CONSTRAINT `archived_tag_post_ibfk_1` FOREIGN KEY (`tag_id`) REFERENCES `tags` (`id`),
  CONSTRAINT `archived_tag_post_ibfk_2` FOREIGN KEY (`archived_post_id`) REFERENCES `archived_posts` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1048575 DEFAULT CHARSET=utf8
```

</details>

## Columns

| Name             | Type             | Default           | Nullable | Children | Parents                             | Comment |
| ---------------- | ---------------- | ----------------- | -------- | -------- | ----------------------------------- | ------- |
| id               | int(11) unsigned |                   | false    |          |                                     |         |
| tag_id           | int(11) unsigned |                   | false    |          | [tags](tags.md)                     |         |
| archived_post_id | int(11) unsigned |                   | false    |          | [archived_posts](archived_posts.md) |         |
| created_at       | datetime         | CURRENT_TIMESTAMP | true     |          |                                     |         |
| updated_at       | datetime         | CURRENT_TIMESTAMP | true     |          |                                     |         |

## Constraints

| Name                     | Type        | Definition                                                    |
| ------------------------ | ----------- | ------------------------------------------------------------- |
| archived_tag_post_ibfk_1 | FOREIGN KEY | FOREIGN KEY (tag_id) REFERENCES tags (id)                     |
| archived_tag_post_ibfk_2 | FOREIGN KEY | FOREIGN KEY (archived_post_id) REFERENCES archived_posts (id) |
| PRIMARY                  | PRIMARY KEY | PRIMARY KEY (id)                                              |

## Indexes

| Name             | Definition                                          |
| ---------------- | --------------------------------------------------- |
| archived_post_id | KEY archived_post_id (archived_post_id) USING BTREE |
| tag_id           | KEY tag_id (tag_id) USING BTREE                     |
| PRIMARY          | PRIMARY KEY (id) USING BTREE                        |

## Relations

![er](archived_tag_post.png)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
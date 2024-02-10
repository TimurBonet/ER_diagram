
![ER diagram](https://github.com/TimurBonet/ER_diagram/blob/main/ER%20diagram.png)

-- Извлечь все фильмы\
SELECT film_id id,\
name\
FROM film;\
\
-- Извлечь топ 10\
SELECT film_id\
FROM film_likes\
ORDER BY COUNT (user_id) DESC\
LIMIT 10;\
\
-- Выбрать друзей пользователя 1\
SELECT user_id2 AS friend_id\
FROM friends\
WHERE user_id1 = 1\ 
AND status = 'true';\
\
--Выбрать общих друзей пользователя 1 и пользователя 3\
SELECT user_id2 AS friend_id\
FROM friends\
WHERE user_id1 = 3 \
AND status = 'true'\
AND friend_id IN \
(SELECT user_id2 AS friend_id\
FROM friends\
WHERE user_id1 = 1\ 
AND status = 'true');

	

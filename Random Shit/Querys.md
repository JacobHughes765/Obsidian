````
SELECT adloginid
FROM hr.tblhr_employees
WHERE employeeid = 2661;
````

````
select urls.id, urls.url, urls.title, urls.visit_count, datetime((last_visit_time/1000000)-11644473600, 'unixepoch'),
visited_links.top_level_url,
visits.external_referrer_url
from urls
inner join visited_links on visited_links.link_url_id = urls.id
inner join visits on visits.url = urls.id

````
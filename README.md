SELECT A.order_id, SUM(A.qty * B.item_weight) AS total_weight

FROM Order_Items AS A

INNER JOIN Items AS B

ON A.item_id = B.item_id

WHERE A.item_id <> (SELECT item_id

FROM Items

WHERE item_name = 'Gizmos')

GROUP BY A.order_id

HAVING SUM((A.qty * B.item-weight) > 10);

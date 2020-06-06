## Distinct

    select distinct city 
    from customer
    order by city;

## Not Exists

    select customer_id
    from customer
    where not exists (select order_id from purshare_order  where customer.customer_id=purshase_order.order_id)

## Having

    select city, count(customer_id) as customer_count
    from customer
    group by  city
    having count(customer_count)>=2;

## Like

## Not Null

## group by

## outer joins

## multiple join

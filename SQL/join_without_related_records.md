# JOIN without related records

JOIN for find elements with removed related records

    select O.id from "Order" as O where not exists (select OI.id from "OrderItem" as OI where OI.order_id = O.id)

or next query

    select O.id from "Order" as O where O.id not in (select OI.order_id from "OrderItem" as OI)

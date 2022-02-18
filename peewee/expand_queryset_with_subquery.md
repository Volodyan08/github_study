# Expand queryset with using subquery

For expand queryset sometime better use subquery without join on new table. For example using SMSHistory.status field

    queryset = OrderItem.select(
                OrderItem,
                SMSHistory.select(SMSHistory.status).where(SMSHistory.relatedObject == Order.id).order_by(SMSHistory.updated.desc()).limit(1).alias('smsStatus')
                )

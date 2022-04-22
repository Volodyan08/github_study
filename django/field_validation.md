# Prefetch for GET List of objects

For optimize query to GET List of objects from many models you can use JOIN models or use  
prefetch. Conveniently define paginator and make prefetch here

    class NewPrefetchPaginator(ModelPaginator):
        def get_page(self, data, page):
            return data.paginate(page, self.page_size).prefetch(
                Cargo.select(
                    Cargo.id, 
                    Cargo.volume, 
                    Cargo.weight, 
                    Cargo.orderItem, 
                    Cargo.partnerCargoId),
                Address.select(
                    Address.id, 
                    Address.city, 
                    Address.street, 
                    Address.number, 
                    Address.area),
                ContactPerson.select(
                    ContactPerson.id, 
                    ContactPerson.lastName, 
                    ContactPerson.firstName, 
                    ContactPerson.phone),
                Area.select(Area.id, Area.timezone),
            )


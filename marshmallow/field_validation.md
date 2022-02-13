# Field validation

For validation field in Marshmallow use @validates

    service = fields.ExtendedPluck(B2BServiceSerializer, required=True)

    @validates("service")
    def validate_service(self, value):
        existing_service = B2BService.select().where(B2BService.id == value).exists()
        if not existing_service:
            raise DELETED_SERVICE_ERROR.exception

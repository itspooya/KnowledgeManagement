# Error Handling and debugging FastAPI

## How it started?

Other day I was writing an API for prometheus Alertmanager with some
additions in mind that would be good, I encountered a problem that my API
kept returning 422 unprocessable entity, but I didn't know what was wrong
and also couldn't view the error due to how Alertmanager works so I looked
for a way to find out what was wrong

After some search and reading multiple answers on stackoverflow I have
found out this piece of code which returned the error

        @app.exception_handler(RequestValidationError)
        async def validation_exception_handler(request: Request, exc: RequestValidationError):
            print(f"Error: {exc.errors()}")
            print(f"Body {exc.body}")
            return JSONResponse(
                status_code=status.HTTP_422_UNPROCESSABLE_ENTITY,
                content=jsonable_encoder({"detail": exc.errors(), "body": exc.body}),
            )

### Answer

I have found the problem finally and it was due to some jobs didn't have
commonLabels and commonAnnotations.



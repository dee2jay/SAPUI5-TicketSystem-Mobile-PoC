# Docker deployment

Build and run:

    docker build -t ticketsystem-mobile .
    docker run --rm -p 8081:80 ticketsystem-mobile

The production build uses the same browser origin for the API and calls /api/....

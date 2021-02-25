Followed this article: https://dev.to/alrobilliard/deploying-net-core-to-heroku-1lfe

1) Added typical .NET Core Dockerfile. Targeted .NET Core 3.1 for simplicity's sake.
2) Tweaked Program.cs based on this issue: https://stackoverflow.com/questions/59434242/asp-net-core-gives-system-net-sockets-socketexception-error-on-heroku
3) Build docker container image: docker build -t moviemvc .
4) Pushed container image to heroku container registry: heroku container:push -a heroku-netcore-test-app web
5) Released container image (released to "prod", basically): heroku container:release -a heroku-netcore-test-app web
6) Profit! http://heroku-netcore-test-app.herokuapp.com/
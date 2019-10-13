FROM ruby
LABEL antonga <antonga@student.wethinkcode.co.za>
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y nodejs sqlite3 build-essential libpq-dev && gem update && gem install rails
ONBUILD EXPOSE 3000
ONBUILD COPY /app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
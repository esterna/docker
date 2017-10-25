FROM ruby

RUN apt-get update -y
RUN apt-get upgrade -y
RUN gem install rails
RUN apt-get install nodejs -y

# port for nodejs
EXPOSE 3000

ONBUILD COPY . /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed

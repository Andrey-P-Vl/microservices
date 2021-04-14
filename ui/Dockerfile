FROM ubuntu:16.04

RUN apt-get update \
&& apt-get install -y ruby-full ruby-dev build-essential \
&& gem install bundler --no-ri --no-rdoc
RUN gem install puma -v '3.10.0'
ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME
ADD Gemfile* $APP_HOME/
RUN bundle install
ADD . $APP_HOME
ENV POST_SERVICE_HOST post
ENV POST_SERVICE_PORT 5000
ENV COMMENT_SERVICE_HOST comment
ENV COMMENT_SERVICE_PORT 9292
CMD ["puma"]


#
#ENV APP_HOME /app
#RUN mkdir $APP_HOME
#WORKDIR $APP_HOME
#RUN gem install puma -v '3.10.0'
#RUN gem install bson_ext -v '1.12.5'
#RUN gem install unf_ext -v '0.0.7.4'
#ADD Gemfile* $APP_HOME/
#RUN bundle install --frozen

#ADD . $APP_HOME

#ENV POST_SERVICE_HOST post
#ENV POST_SERVICE_PORT 5000
#ENV COMMENT_SERVICE_HOST comment
#ENV COMMENT_SERVICE_PORT 9292

#CMD ["puma"]

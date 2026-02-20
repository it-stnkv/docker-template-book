FROM ruby:3.3-alpine

WORKDIR /app

RUN apk add --no-cache build-base postgresql-dev

COPY Gemfile Gemfile.lock ./
RUN bundle install --without development test

COPY . .

RUN adduser -D appuser
USER appuser

CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]

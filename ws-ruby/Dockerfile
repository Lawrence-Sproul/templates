FROM cloud9/workspace
MAINTAINER Cloud9 IDE, inc. <info@c9.io>

RUN echo "Version 1.0"

    
USER ubuntu

RUN bash -l -c "rvm install 2.4.5 && \
    rvm use 2.4.5 --create && \
    NOKOGIRI_USE_SYSTEM_LIBRARIES=1 gem install rails -v 5.2.2"
RUN bash -l -c "rvm install 2.5.3 && \
     rvm use 2.5.3 --create && \
     NOKOGIRI_USE_SYSTEM_LIBRARIES=1 gem install rails -v 5.2.2"
RUN bash -l -c "rvm install ruby-2.6.0 && \
    rvm use 2.6.0 --create && \
    NOKOGIRI_USE_SYSTEM_LIBRARIES=1 gem install rails -v 5.2.2"

USER root
RUN rm -rf /home/ubuntu/workspace
ADD ./files/workspace /home/ubuntu/workspace
RUN chown -R ubuntu:ubuntu /home/ubuntu

USER ubuntu
RUN bash -l -c "rails new /home/ubuntu/workspace"

USER root

ADD ./files/check-environment /.check-environment/ruby

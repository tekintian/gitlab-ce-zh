FROM gitlab/gitlab-ce:8.15.5-ce.0
ENV GITLAB_VERSION=v8.15.5
RUN set -xe \
    && echo " # Generating translation patch ..." \
    && git clone https://gitlab.com/xhang/gitlab.git \
    && cd gitlab \
    && git diff v8.15.5..v8.15.5-zh > ../zh_CN.diff \
    && echo " # Patching ..." \
    && patch -d /opt/gitlab/embedded/service/gitlab-rails -p1 < ../zh_CN.diff \
    && echo " # Cleaning ..." \
    && cd .. \
    && rm -rf gitlab \
    && rm *.diff

# fluentd-idp-sample

EC2上のインスタンスで、侵入検知を行った設定です。  
`/var/log/secure` を監視し、mackerelへログイン関連の回数の記録、slackへログイン通知を行います。

## setup
```
% curl -L http://toolbelt.treasuredata.com/sh/install-redhat-td-agent2.sh | sudo sh
% sudo /opt/td-agent/embedded/bin/fluent-gem install fluent-plugin-datacounter
% sudo /opt/td-agent/embedded/bin/fluent-gem install fluent-plugin-mackerel
% sudo /opt/td-agent/embedded/bin/fluent-gem install fluent-plugin-slack
% sudo /opt/td-agent/embedded/bin/fluent-gem install fluent-plugin-rewrite-tag-filter
% sudo chgrp td-agent /var/log/secure
% sudo chmod 640 /var/log/secure
% sudo ls -l /var/log/secure
```
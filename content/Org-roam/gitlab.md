---
publish: true
title: Gitlab
created: 2022-02-12T12:37:54
modified: 2026-08-05T07:58:56.684Z
---

# Gitlab

# Troubleshooting

## Artifacts\[fn:1]

### Delete artifacts older than a specific date

From ~gitlab-rails console~:
builds\_to\_clear = builds\_with\_artifacts.where("finished\_at < ?", 1.week.ago)
builds\_to\_clear.find\_each do |build|
build.artifacts\_expire\_at = Time.now
build.erase\_erasable\_artifacts!
end

The same can be done to include logs as well:
builds\_to\_clear = builds\_with\_artifacts.where("finished\_at < ?", 1.week.ago)
builds\_to\_clear.find\_each do |build|
print "Ci::Build ID #{build.id}... "

if build.erasable?
build.erase(erased\_by: admin\_user)
puts "Erased"
else
puts "Skipped (Nothing to erase or not erasable)"
end
end

### Expiration cron job

In ~/etc/gitlab/gitlab.rb~ enable ~gitlab\_rails\['expire\_build\_artifacts\_worker\_cron'] = "\*/7 \* \* \* \*"~.

# Footnotes

\[fn:1] https://docs.gitlab.com/ee/administration/job\_artifacts.html

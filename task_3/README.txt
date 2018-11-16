Add template to your directory with homework-3. Update hits service whit relevant build information. Please use hits:h4
suffix for image name. Please push the image with docker-compose push .
Then, you need to configure docker-compose.yml in a way, when the log file is shared across all 'hits' instances. To test it, scale
hits service at least up to 3 instances, curl localhost:8080 a couple of times, call curl localhost:8080/logs . You should see
messages for all your received ids.
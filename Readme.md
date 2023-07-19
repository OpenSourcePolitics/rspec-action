# RSpec action

This action runs [RSpec](https://rspec.info/) tests.

## Inputs
- ruby_version:
  - description: 'Ruby Version'
  - required: false
  - default to RUBY_VERSION environment variable
- node_version:
  - description: 'Node Version'
  - required: false
  - default to NODE_VERSION environment variable
- command:
  - description: 'Command to run'
  - required: true
  - default: 'bundle exec rspec'
- prepare_command:
  - description: 'Command to run before rspec'
  - required: true
  - default: 'bundle exec rake test_app'

## Example usage
    
```yaml
- name: Run RSpec
  uses: OpenSourcePolitics/rspec-action@master
```

To exclude system tests, you can use the following command:

```yaml
- name: Run RSpec
  uses: OpenSourcePolitics/rspec-action@master
  with:
    command: 'bundle exec rspec --exclude-pattern "spec/system/**/*_spec.rb"'
```

To use in an app that doesn't require a test_app, you can use the following command:

```yaml
- name: Run RSpec
  uses: OpenSourcePolitics/rspec-action@master
  with:
    prepare_command: 'bundle exec rails db:create db:migrate'
```

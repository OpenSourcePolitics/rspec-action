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

## Example usage
    
```yaml
- name: Run RSpec
  uses: OpenSourcePolitics/decidim-action-rspec@master
```

To exclude system tests, you can use the following command:

```yaml
- name: Run RSpec
  uses: OpenSourcePolitics/decidim-action-rspec@master
  with:
    command: 'bundle exec rspec --exclude-pattern "spec/system/**/*_spec.rb"'
```
# Collaborative Text Editor

## Install Ruby:

[Download Ruby](https://rubyinstaller.org/downloads/)

## Install Rails using gem:

```bash
gem install rails
```

##  Setup Rails Project

# Create new Rails project with PostgreSQL
```bash
rails new collaborative-editor --database=postgresql --webpack=react
```

## Install additional dependencies:

```bash
bundle add redis
bundle add sidekiq
```

## To create test and development databases:

```bash
rails db:create

rails db:migrate
```

## Example usage:

```bash
# Creating a document
doc = Document.create(content: "Hello", version: 1)

# Inserting text
operation = OpenStruct.new(type: :insert, position: 5, text: " World")
doc.apply_operation(operation)
# Result: "Hello World"

# Deleting text
operation = OpenStruct.new(type: :delete, position: 5, length: 6)
doc.apply_operation(operation)
# Result: "Hello"
```

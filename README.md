# Debugging a database-backed web application

## Learning Objectives

- Define 'debugging' as the process of eliminating bugs from an expected program output.
- Explain the mantra 'Tighten the loop; Get visibility'.
- Use the mantra to resolve bugs across the web stack.

## Instructions

In this program, there are five bugs.

- Find the bugs and fix them.
- You need to get all the tests passing.
- You need to run the app and make sure it works.

Use this debugging method:

- Tighten the loop
  - Find the exact line which triggers the bug and when that line is executed.
- Get visibility
  - What _should_ be happening on and around that line.
  - Investigate whether that is actually being achieved.
- Once you know the _one thing_ that is wrong, out of place, misspelled, or not giving you what you expect, try to fix it.
- If your attempts to fix the bug do not change the error message, be _very_ suspicious and seriously consider reverting that change!


## Setup

* Get the code and install the gems

```
git clone git@github.com:EdwardAndress/DebugBookmarkManager.git
cd DebugBookmarkManager
bundle install
```

* Set up the database

```
psql
CREATE DATABASE debug_bookmark_manager;
\c debug_bookmark_manager
CREATE TABLE bookmarks(id SERIAL PRIMARY KEY, title VARCHAR(60), url VARCHAR(60));
CREATE DATABASE debug_bookmark_manager_test;
\c debug_bookmark_manager_test
CREATE TABLE bookmarks(id SERIAL PRIMARY KEY, title VARCHAR(60), url VARCHAR(60));
```

## Run the tests

- Run the tests with `rspec`.

## Run the app

- Run the app with `shotgun`.  This will automatically reload your changes so you don't need to restart your server on each code change.

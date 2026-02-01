
# COM3420 - Software Hut

## About WOOT

WOOT is a real-time interactive quiz platform inspired by Kahoot, built for educational environments. It enables teachers to create engaging quiz experiences and run live sessions with their students.

🏆 **Software Hut Prize Winner** — Recognized for outstanding software development for a real-world client.

### Key Features

- **Quiz Creation & Management:** Teachers can create custom quizzes with multiple-choice questions, organize them into folders, and reuse them across sessions.
- **No Account Required for Students:** Students join quiz sessions instantly using a simple game code, no sign-up or login needed.
- **Live Interactive Sessions:** Once a session starts, students see questions update in real-time on their devices. Teachers control the pace, advancing through questions while monitoring live participation.
- **Real-time Synchronization:** All participants stay in sync throughout the quiz. When the teacher moves to the next question, every student's screen updates simultaneously, creating a dynamic and engaging classroom experience.
- **Real-time Updates:** Due to server restrictions, this project could not leverage WebSockets to achieve live interaction between users. Instead, it uses **Server-Sent Events (SSE)** combined with **PostgreSQL's LISTEN/NOTIFY pub/sub mechanism** to deliver real-time updates to participants during quiz sessions.

## SETTING UP THE APP ON YOUR MACHINE

After cloning the repo, make sure to execute the following commands:

- Install dependencies:

```cp config/database-sample.yml config/database.yml```

```bundle install```

```yarn install```

- Set up the database:

```bundle exec rails db:create```

```bundle exec rails db:migrate```

```bundle exec rails db:seed```

## RUNNING THE APP

- Start the Rails server:
```bundle exec rails s```

- In separate terminal window, start the webpack dev server:
```bin/webpacker-dev-server```

- Open ```http://127.0.0.1:3000/``` in your browser to access the app.

- Press ```CTRL+C``` to stop the app.

## ESSENTIALS BEFORE PUSHING/OPENING PR

Remember to perform following tasks before you ```git push``` or open your Pull Request.

Make sure you are in the root of the project directory.

- Run HAML linter (if any issues appear, you have to fix them manually):
```bundle exec haml-lint```

- Run Rubocop linter:
```bundle exec rubocop```

- If there are any issues, they can be fixed running:
```bundle exec rubocop -A```

- Run RSpec tests:
```bundle exec rspec spec```

## DEPLOYMENT INSTRUCTIONS

- After the first deployment (which was slightly more complex), all you need to deploy a new release is to run the following command:
```bundle exec epi_deploy release -d demo```

- The website can be accessed following the link:
[woot-demo](https://team22.demo4.hut.shefcompsci.org.uk/)
# WOOT

# Game-Capital-Quiz

This is a fun and interactive web application where users can test their knowledge of world capitals. The application fetches country and capital data from a PostgreSQL database and presents a random country for the user to guess its capital.

---

## Features
- Random country is presented for users to guess the capital.
- Tracks the user's total correct answers (score).
- Provides immediate feedback on whether the answer is correct or not.
- Alerts the user when the game is over and displays their best score.
- Option to restart the game.
- Uses a PostgreSQL database to fetch country and capital data dynamically.

---

## Technologies Used

### Backend
- **Node.js**
- **Express.js**
- **PostgreSQL**

### Frontend
- **HTML5**
- **CSS**
- **JavaScript**

---

## Prerequisites

Ensure you have the following installed:
1. [Node.js](https://nodejs.org/)
2. [PostgreSQL](https://www.postgresql.org/)

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/RahulRmCoder/Game-Capital-Quiz.git
cd Game-Capital-Quiz
```

### 2. Install Dependencies
Run the following command to install the required dependencies:
```bash
npm install
```

### 3. Configure PostgreSQL Database

1. Ensure PostgreSQL is running.
2. Create a database named `world`.
3. Create a table named `capitals` with the following schema:
   ```sql
   CREATE TABLE capitals (
       id SERIAL PRIMARY KEY,
       country VARCHAR(255) NOT NULL,
       capital VARCHAR(255) NOT NULL
   );
   ```
4. Populate the table with sample data:
   ```sql
   INSERT INTO capitals (country, capital) VALUES
   ('France', 'Paris'),
   ('United Kingdom', 'London'),
   ('United States of America', 'New York');
   ```

### 4. Update Database Connection
Open the `index.js` file and update the PostgreSQL connection details:
```javascript
const db = new pg.Client({
    user: "postgres",
    host: "localhost",
    database: "world",
    password: "your_password",
    port: 5432,
});
```
Replace `your_password` with your PostgreSQL password.

### 5. Start the Server
Run the server using:
```bash
node index.js
```
The server will start at [http://localhost:3002](http://localhost:3002).

---

## File Structure
```
Indian-Cricket-Players-Stats/
├── public/
│   └── styles/
│       └── main.css  # CSS file for styling the application
├── views/
│   └── index.ejs     # EJS template for rendering the game
├── index.js          # Main server-side script
└── README.md         # Project documentation
```

---

## Usage
1. Open your browser and go to `http://localhost:3002`.
2. Guess the capital of the displayed country and submit your answer.
3. The application will indicate whether your answer is correct and update your score.
4. When the game ends, a message will alert you, and you can restart.

---

## Future Enhancements
- Add a timer to make the game more challenging.
- Implement user authentication and leaderboard functionality.
- Support multiple languages for country names and capitals.
- Add difficulty levels based on the region or number of countries.

---

## License
This project is licensed under the MIT License. Feel free to use and modify it as per your needs.

---

## Contributions
Contributions are welcome! Feel free to submit a pull request or open an issue in the repository.

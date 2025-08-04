# Quiz-Game-

import time
import random

 
questions = [
    {
        "question": "What is the capital of France?",
        "options": ["A. London", "B. Berlin", "C. Paris", "D. Madrid"],
        "answer": "C"
    },
    {
        "question": "Who developed Python?",
        "options": ["A. Dennis Ritchie", "B. Guido van Rossum", "C. Bjarne Stroustrup", "D. James Gosling"],
        "answer": "B"
    },
    {
        "question": "What is 5 * 6?",
        "options": ["A. 11", "B. 56", "C. 30", "D. 35"],
        "answer": "C"
    },
    {
        "question": "Which language is used for web apps?",
        "options": ["A. Python", "B. JavaScript", "C. C++", "D. Java"],
        "answer": "B"
    }
]

 
random.shuffle(questions)

 
score = 0
print("\n🎉 Welcome to the Python Quiz!\nYou have 10 seconds per question.\n")

for i, q in enumerate(questions):
    print(f"\nQuestion {i + 1}: {q['question']}")
    for opt in q["options"]:
        print(opt)

    start_time = time.time()
    try:
        answer = input("Your answer (A/B/C/D): ").upper()
        elapsed = time.time() - start_time

        if elapsed > 10:
            print("⏰ Time's up!")
        elif answer == q["answer"]:
            print("✅ Correct!")
            score += 1
        else:
            print(f"❌ Wrong! Correct answer: {q['answer']}")
    except Exception as e:
        print("Error:", e)

 

print(f"\n🏁 Quiz Finished!\nYour Score: {score}/{len(questions)}")

if score == len(questions):
    print("🎉 Perfect score! You're a pro!")
elif score >= len(questions) // 2:
    print("💪 Good job! Keep practicing.")
else:
    print("🧠 Don't worry! Try again and you'll improve.")

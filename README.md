# import random

# Define quiz questions and answers
quiz_questions = {
    "What is the capital of France?": "Paris",
    "Who wrote 'Romeo and Juliet'?": "William Shakespeare",
    "What is the largest planet in our solar system?": "Jupiter",
    "What is the powerhouse of the cell?": "Mitochondria",
    "What is the chemical symbol for water?": "H2O"
}

def display_welcome_message():
    print("Welcome to the Quiz Game!")
    print("You will be presented with multiple-choice questions.")
    print("Select the correct answer to earn points.\n")

def present_quiz_questions():
    questions = list(quiz_questions.keys())
    random.shuffle(questions)
    score = 0

    for question in questions:
        print(question)
        user_answer = input("Your answer: ")
        correct_answer = quiz_questions[question]
        if user_answer.lower() == correct_answer.lower():
            print("Correct!\n")
            score += 1
        else:
            print(f"Incorrect! The correct answer is: {correct_answer}\n")
    
    return score

def display_final_results(score):
    print("Quiz completed!")
    print(f"Your final score is: {score}/{len(quiz_questions)}")
    if score == len(quiz_questions):
        print("Congratulations! You got all the questions correct.")
    elif score >= len(quiz_questions) / 2:
        print("Well done! You got more than half of the questions correct.")
    else:
        print("You can do better! Keep practicing.")

def play_again():
    choice = input("Do you want to play again? (yes/no): ")
    return choice.lower() == 'yes'

def main():
    while True:
        display_welcome_message()
        score = present_quiz_questions()
        display_final_results(score)
        if not play_again():
            break

if __name__ == "__main__":
    main()

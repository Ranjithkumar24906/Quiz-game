# Quiz-game
def ask_question(question, options, answer):
    print("\n" + question)
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")
    try:
        choice = int(input("Your choice (1-4): "))
        if options[choice - 1].lower() == answer.lower():
            print("Correct!")
            return 1
        else:
            print(f"Wrong! The correct answer was: {answer}")
            return 0
    except (ValueError, IndexError):
        print("Invalid input!")
        return 0

def main():
    questions = [
        ("What is the capital of France?", ["Berlin", "London", "Paris", "Rome"], "Paris"),
        ("Which planet is known as the Red Planet?", ["Earth", "Mars", "Jupiter", "Venus"], "Mars"),
        ("Who wrote 'Hamlet'?", ["Shakespeare", "Dante", "Homer", "Tolstoy"], "Shakespeare"),
        ("What is the largest ocean?", ["Atlantic", "Arctic", "Indian", "Pacific"], "Pacific")
    ]
    score = 0
    for q, opts, ans in questions:
        score += ask_question(q, opts, ans)
    print(f"\nYour final score: {score}/{len(questions)}")

if __name__ == "__main__":
    main()

# AdithyanCB
AI CHATBOT
import re
import random

class RuleBasedBot:
    def __init__(self):
        # Define intent patterns using regular expressions
        self.rules = {
            'greeting': r'\b(hi|hello|hey|greetings|hola)\b',
            'goodbye': r'\b(bye|goodbye|exit|quit|see you)\b',
            'how_are_you': r'\b(how are you|how\'s it going|how do you do)\b',
            'name_query': r'\b(your name|who are you)\b',
            'help_query': r'\b(help|support|assist)\b'
        }
        
        # Mapping intents to a collection of potential responses
        self.responses = {
            'greeting': [
                "Hello! How can I help you today?", 
                "Hey there! What can I do for you?", 
                "Greetings! How may I assist you?"
            ],
            'goodbye': [
                "Goodbye! Have a great day!", 
                "Bye! Feel free to chat again anytime.", 
                "See you later!"
            ],
            'how_are_you': [
                "I am just a collection of rules, but I am running perfectly!", 
                "Doing great! Ready to answer your questions.", 
                "I'm functioning optimally, thank you!"
            ],
            'name_query': [
                "I am EchoBot, a simple rule-based AI.", 
                "You can call me EchoBot. I run on Python logic!"
            ],
            'help_query': [
                "I can answer basic greetings, state my name, or say goodbye.", 
                "Tell me what you need, and I will try to match it to my rules."
            ],
            'fallback': [
                "I'm sorry, I didn't quite understand that. Could you rephrase?", 
                "My rules don't cover that phrase yet. Can you try asking differently?", 
                "Interesting point, but I'm not sure how to respond to that."
            ]
        }

    def match_intent(self, user_message):
        """Scan the user input against predefined regex rules to find a matching intent."""
        for intent, pattern in self.rules.items():
            # Perform case-insensitive regex matching
            if re.search(pattern, user_message, re.IGNORECASE):
                return intent
        return 'fallback'

    def generate_response(self, user_message):
        """Determine intent and pull a random response from that category."""
        intent = self.match_intent(user_message)
        # Choose a random response from the matched intent list
        return random.choice(self.responses[intent]), intent

    def start_chat(self):
        """Launch the interactive chat loop in the console."""
        print("==================================================")
        print("EchoBot: Hello! I am a rule-based system. (Type 'exit' to quit)")
        print("==================================================")
        
        while True:
            user_input = input("You: ").strip()
            if not user_input:
                continue
                
            response, intent = self.generate_response(user_input)
            print(f"EchoBot: {response}")
            
            if intent == 'goodbye':
                break

# Run the chatbot application
if __name__ == "__main__":
    bot = RuleBasedBot()
    bot.start_chat()

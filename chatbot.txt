import random
import nltk
from nltk.corpus import wordnet
from colorama import init, Fore, Back, Style




init(convert=True)
print(Fore.CYAN + 'Welcome to Chatbot!')
print(Style.RESET_ALL)





userInput = input()
synonyms = []
infiniteLoop=True
type(userInput)
starter = ["hi"]
questions = ["how are you?"]
answers = ["good", "horrible"]
goodbyes = ["bye"]





while infiniteLoop:
    if userInput.lower() in starter:
        synonyms = []
        for syn in wordnet.synsets(random.choice(starter)):
            for lemma in syn.lemmas():
                synonyms.append(lemma.name())
        print(Fore.CYAN + random.choice(synonyms))
        print(Style.RESET_ALL)        
        userInput = input()
         
    elif userInput.lower() in questions:
        synonyms = []
        for syn in wordnet.synsets(random.choice(answers)):
            for lemma in syn.lemmas():
                synonyms.append(lemma.name())
        print(Fore.CYAN + random.choice(synonyms))
        print(Style.RESET_ALL)         
        userInput = input()
            
    elif userInput.lower() in goodbyes:
        synonyms = []
        for syn in wordnet.synsets(random.choice(goodbyes)):
            for lemma in syn.lemmas():
                synonyms.append(lemma.name())
        print(Fore.CYAN + random.choice(synonyms))
        print(Style.RESET_ALL)     
        userInput = input()
          



    else:
        print (Fore.CYAN + "I'm not sure how to respond...")

        print(Style.RESET_ALL)
        userInput = input()
        synonyms = []
                


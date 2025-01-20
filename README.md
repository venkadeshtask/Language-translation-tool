# Language-translation-tool
Using python
from googletrans import Translator

def translate_text():
    print("Welcome to the Language Translation Tool!")
    print("Enter 'exit' at any time to quit.")
    
    # Create a Translator object
    translator = Translator()
    
    while True:
        # Input text to translate
        text = input("\nEnter text to translate: ")
        if text.lower() == 'exit':
            print("Exiting the translation tool. Goodbye!")
            break
        
        # Input source language (e.g., 'en' for English, 'es' for Spanish)
        src_lang = input("Enter the source language (e.g., 'en' for English): ").strip()
        if src_lang.lower() == 'exit':
            print("Exiting the translation tool. Goodbye!")
            break
        
        # Input target language
        target_lang = input("Enter the target language (e.g., 'es' for Spanish): ").strip()
        if target_lang.lower() == 'exit':
            print("Exiting the translation tool. Goodbye!")
            break
        
        try:
            # Translate the text
            translation = translator.translate(text, src=src_lang, dest=target_lang)
            print(f"Translation ({src_lang} -> {target_lang}): {translation.text}")
        except Exception as e:
            print(f"Error occurred during translation: {e}")

if __name__ == "__main__":
    translate_text()

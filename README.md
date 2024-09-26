class Game:
    def __init__(self, language='en'):
        self.language = language
        self.translations = {
            'en': {
                'welcome': "Welcome to the RPG Game!",
                'choose_language': "Choose your language: (1) English (2) 中文",
                'exit': "Thanks for playing!",
                'enemy_encounter': "You encountered an enemy!",
                'attack': "You attack the enemy!",
                'win': "You defeated the enemy!",
                'lose': "You were defeated by the enemy.",
            },
            'zh': {
                'welcome': "欢迎来到RPG游戏！",
                'choose_language': "选择你的语言: (1) English (2) 中文",
                'exit': "感谢你的游戏!",
                'enemy_encounter': "你遇到了敌人！",
                'attack': "你攻击了敌人！",
                'win': "你打败了敌人！",
                'lose': "你被敌人打败了。",
            }
        }

    def start(self):
        print(self.translations[self.language]['welcome'])
        self.set_language()
        self.play()

    def set_language(self):
        choice = input(self.translations[self.language]['choose_language'] + "\n")
        if choice == '1':
            self.language = 'en'
        elif choice == '2':
            self.language = 'zh'

    def play(self):
        print(self.translations[self.language]['enemy_encounter'])
        action = input("Press 'a' to attack: ")
        if action.lower() == 'a':
            print(self.translations[self.language]['attack'])
            # Simulating a win/lose condition
            import random
            if random.choice([True, False]):
                print(self.translations[self.language]['win'])
            else:
                print(self.translations[self.language]['lose'])
        else:
            print(self.translations[self.language]['exit'])

if __name__ == "__main__":
    game = Game()
    game.start()# -1

Assignment 1: Design Your Own Class! 🏗️ and Activity 2: Polymorphism Challenge! 🎭


# Base class
class Character:
    def __init__(self, name, origin, power_level):
        self.name = name
        self.origin = origin
        self._power_level = power_level  # Encapsulated attribute

    def get_power_level(self):
        return self._power_level

    def set_power_level(self, new_level):
        if new_level >= 0:
            self._power_level = new_level
        else:
            print("Power level must be non-negative.")

    def introduce(self):
        return f"I am {self.name} from {self.origin}."

# Subclass: Superhero
class Superhero(Character):
    def __init__(self, name, origin, power_level, superpowers):
        super().__init__(name, origin, power_level)
        self.superpowers = superpowers

    def use_power(self):
        return f"{self.name} uses {', '.join(self.superpowers)}!"

    def introduce(self):
        return f"Superhero {self.name} from {self.origin}, ready to save the day!"

# Subclass: Villain
class Villain(Character):
    def __init__(self, name, origin, power_level, evil_plan):
        super().__init__(name, origin, power_level)
        self.evil_plan = evil_plan

    def execute_plan(self):
        return f"{self.name} is executing their evil plan: {self.evil_plan}"

    def introduce(self):
        return f"Villain {self.name} from {self.origin}, plotting doom!"

# Polymorphism in action
def character_intro(character):
    print(character.introduce())

# Example usage
hero = Superhero("Nova Blaze", "Galactic Core", 95, ["Photon Blast", "Flight"])
villain = Villain("Dark Vortex", "Shadow Realm", 90, "Engulf the Earth in darkness")

character_intro(hero)      # Polymorphic call
character_intro(villain)   # Polymorphic call

print(hero.use_power())
print(villain.execute_plan())

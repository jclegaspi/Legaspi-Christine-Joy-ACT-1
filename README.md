import random
character_health = 100
monster_health = 100
Health_Attack = 100
item = ""


name = input("Enter your name: ")
print("Hello " + name)

while character_health > 0:
    if character_health != 100 and item == "Fish":
        n = input("You have taken some damage to heal select [1 to heal/ 0 to ignore]")
        if n == "1":      
            character_health += 10
            print("Your character's health is back to " + str(character_health)) 
        else:          
             print("Your character's health is back to " + str(character_health))

    elif character_health != 100 and item == "Shadow Guardian":
                n = input("you have chance to heal !!using your:" + item + "!\n" + "[press 1 to heal]")
                   
                character_health += 100 
                print("character_health + 100!\n" + "Your Character_Health is Now: "+ str(Character_Health))

             
       
       
    v = int(input("Choose 1 if you want to cross the river\nChoose 2 if you want to jump on the ravine\nChoose 3 if you want to fight monster in the dungeon \n"))  

               #Start of Journey
    if v == 1:
        choice = input("If you want to go fishing select [1 for yes/ 0 for no]")
        if choice == "1":
       
           #Fishing minigame
            print("You have chosen Fishing! ")
            chance = random.randint(0,9)
            if chance > 6:
                item = "Fish"          
                print("You have catch a Fish!")
            else:  print("There is no fish to catch")
        elif v == 2: 
            #damages the player
             print("You have jumped into the ravine")
             print("Your character has taken 10pt of damage")
             character_health = character_health - 10
        elif v == 3:
        #damages the player
              print("You have enter the dungeon")

        #monster attack
        chance = random.randint(0,9)
        if chance > 5:
            
            print ("A Monster Appeared !!!")
            choice = input("Fight the The monster! \n \t [1 to fight using your Basic attack and 0 for to fight using your super Power]")
            if choice == "1":
                print ("You dealt normal damage using your basic attack! monster taken -20hp")
                print ("Your Character taken some damage from the monster!")
                character_health -= 20
                monster_health -= 20
                print ("monster Health: " + str (monster_health))
            elif choice == "0":
                print ("You dealt critical damages using your Ultimate attack! monster taken -30hp")
                print ("Your Character taken some damage from the monster! -20")
                character_health -= 20
                monster_health -= 30
                print ("monster Health: " + str (monster_health))

            if monster_health <= 0:
                print("you have sucessfully deafeated the monster! and gain new item! ")
                item = " Sword"
                print ("You have found " + item + "! \n")
               
        else:
            print ("An monster appeared!")
            choice =  input("Fight the monster! \n \t [1. to Fight using your crossbow, or 0 to Fight using your shotgun]")
            if choice == "1":
                print ("you faught using your crossbow!monster taken -60")
                print ("your character taken some damage from the attack of the monster! -20")
                character_health -= 30
                monster_health -= 60
                print ("monster Health: " + str (monster_health))
            elif choice == "0":
                print ("you fought using your shotgun! monster taken -20")
                print ("your character taken some damages from the attack of the monster! -20")
                character_health -= 30
                monster_health -= 20
                print("monster Health:" + str(monster_health))
                item = " Potion"
                print ("You have found " + item + "! \n")


            if monster_health <= 0:
                print("you have sucessfully deafeated the monster! and gain new item! ")
                item = " Shadow guardian"
                print ("You have found " + item + "! \n")

    else:
            print ("Your Health Attack!")
            choice =  input("if you win the battle you get the another points \n \t [2. points + 10, or 0 you don't want points]")
            if choice == "2":
                print ("when you kill the first monster extra points + 15")
                print ("but if you are defeated in the first battle there is a deduction in that score -20")
                character_health -= 30
                monster_health -= 60
                print ("Health_Attack: " + str (Health_Attack))
            elif choice == "0":
                print ("you fought using your shotgun! monster taken -20")
                print ("your character taken some damages from the attack of the monster! -30")
                character_health -= 30
                monster_health -= 20
                print("Health Attack:" + str(Health_Attack))
                item = " Potion of energy"
                print ("You have found " + item + "! \n")


            if monster_health <= 0:
                print("you have sucessfully deafeated the monster! and gain new item! ")
                item = " Shadow Clone"
                print ("You have found " + item + "! \n")





else:
                print("Invalid input")
print("Your character's Health: " + str(character_health))
print("Your Character is dead!")

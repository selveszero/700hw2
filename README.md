# HW2
Part 2:
For this part, I upload the word-sense-annotations.json file that I created in part 1, and then parse to get the hypernyms and hyponyms dictionaries which are then used to generate the alternative_commands dictionary as in part 1. 
In parse_command function, before doing anything else, I first check if a user command matches an alternative sentence in the alternative_commands dictionary. If yes, then replace it with the known command.
In get_player_intent and run_special_command functions, if failing to exactly match the user command with a known command, I use the find_most_similar_command to determine the most similar known command, and if the similarity is > 0.3 (some threshold I found), then I proceed with that most similar known command.

Part 3:
I used dependency parsing to detect the direct object in the player’s command, and then try to match that with a hardcoded verb-object command.

It works for some commands but not others: 
  You wake up in a classroom full of students.
  Exits: Vault window, Go door
  You see: 
  a plastic bag in the trash can
  a wallet right in front of you
  >take the large plastic bag from trash can
  Sentence: 
  take the large plastic bag from trash can
  You take the bag.
  >take the black wallet
  Sentence: 
  take the black wallet
  You take the wallet.
  >go through the door
  Sentence: 
  go through the door
  I'm not sure what you want to do.

But this works:
  >go the door
  Sentence: 
  go the door
  You are in the hallway of the building.
  
Namely, if the verb is followed by a preposition, there will be no verb_object pair found using the function from part 3. 
  

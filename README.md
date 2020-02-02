# HW2
Part 2:
For this part, I upload the word-sense-annotations.json file that I created in part 1, and then parse to get the hypernyms and hyponyms dictionaries which are then used to generate the alternative_commands dictionary as in part 1. 
In parse_command function, before doing anything else, I first check if a user command matches an alternative sentence in the alternative_commands dictionary. If yes, then replace it with the known command.
In get_player_intent and run_special_command functions, if failing to exactly match the user command with a known command, I use the find_most_similar_command to determine the most similar known command, and if the similarity is > 0.3 (some threshold I found), then I proceed with that most similar known command.

Part 3:

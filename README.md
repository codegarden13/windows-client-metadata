
# 'How' is the Usage of a Workplace ?
## Goal: Dataset about a windows machine's usage.

This powershell will make a number from users and their last usage of that computer this year. We get a timespan, the user list and a magic factor. 

- Who has been using this computer during this year. 
- When did each of this users use this client last time. 
- Timespan (daycount) between first and last usage over all profiles which have been active this year.

## Sidenotes
- Testing was done against last writetime of each user's profile. 
- Result for lastwritetime of each profile folder corresponds to the last file change of ntuserdat.pol of the profile.
- Ntuser.dat's timestamp is not a sufficiant, as it changes at each cumulative update over all profiles. (The existance of this file has been used as indicator if the folder is a real user profile.)

## Get the magic factor
Divide two results to get a valid factor:
```
(Count of days between all that last usages of that machine) / (count of that active profiles)
```
## Final Result:

A factor which may be usable to describe usage-density.

A date-range, when the machine has been used and from which user.

## Thesis
Factor tends to zero: one user is using the machine. 
Factor is high, more users depend on that machine in the given daterange (for now: This year)
Maxybe the factor helpd to find real "Standard - Clients"
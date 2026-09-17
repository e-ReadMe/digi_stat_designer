# digi_stat_designer
A tool I had made with Chat-gpt, to make the process of allocating stats on Digimon and organizing their digivolutions easier. Can be accessed at https://e-readme.github.io/digi_stat_designer/

To be used with the species info document - https://github.com/e-ReadMe/pokeemerald-expansion_Project_ReLoad/blob/master/src/data/pokemon/species_info/digi_1997_1999.h

and with the digivolutions list - https://github.com/e-ReadMe/pokeemerald-expansion_Project_ReLoad/blob/master/src/data/pokemon/digivolution.h

E.g.
```
Take species base stats, e.g. 
	[SPECIES_AGUMON] =
    {
        .baseHP        = 58,
        .baseAttack    = 64,
        .baseDefense   = 58,
        .baseSpAttack  = 80,
        .baseSpDefense = 65,
        .baseSpeed     = 80,

And digivolution list, e.g.
static const struct Digivolution sAgumonDigivolveTable[] = {
//  HP Atk Def SA SD Spd
    {0, 0, 0, 0, 0, 0, SPECIES_GREYMON},
    {0, 0, 0, 0, 0, 0, SPECIES_TYRANNOMON},
    {0, 0, 0, 0, 0, 0, SPECIES_COELAMON},
    {0, 0, 0, 0, 0, 0, SPECIES_CYCLOMON},
    {0, 0, 0, 0, 0, 0, SPECIES_KOROMON}, //Devolve. Keep as the last spot
    DIGIVOLUTION_END
};
```
<img width="1521" height="3495" alt="e-readme github io-digi_stat_designer2" src="https://github.com/user-attachments/assets/3e12a000-add0-401d-aa42-8cd9df4ac2ed" />
The tool allows you to predict roughly what levels the species will be able to evolve at for different targets. Once your done, it can be exported. Note that it must be copy-pasted back into the code manually. 

```
//SPECIES_TSUNOMON
static const struct Digivolution sTsunomonDigivolveTable[] = {
//  HP Atk Def SA SD Spd
    {0, 24, 0, 0, 0, 0, SPECIES_GABUMON}, // 9/15/20
    {0, 0, 0, 19, 0, 0, SPECIES_ELECMON}, // 8/15/22
    #if digi_2000
    {0, 0, 0, 24, 0, 0, SPECIES_ELECMONV}, // 10/20/28
    {0, 30, 0, 0, 0, 0, SPECIES_GABUMONB}, // 12/20/26
    #endif
    {0, 0, 22, 0, 0, 0, SPECIES_PSYCHEMON}, // 9/18/25
    {0, 0, 0, 0, 0, 0, SPECIES_PUNIMON}, // devolution. Keep as the last spot
    DIGIVOLUTION_END
};
```

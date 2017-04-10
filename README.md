# allen CCF tools

Some code to work with the Allen Inst CCF data, specifically the 10µm voxel 2016 version. 

## Usage example:
```
>> tv = readNPY('template_volume_10um.npy'); % grey-scale "background signal intensity"
>> av = readNPY('annotation_volume_10um_by_index.npy'); % 
>> st = loadStructureTree('structure_tree_safe.csv');
>> f = allenAtlasBrowser(tv, av, st);
```

## Requirements
You need the npy-matlab repository to load the data: https://github.com/kwikteam/npy-matlab

You also need the data files. See //zserver/Lab/Atlas/allenCCF or, if you don't have access to that, contact me at nick.steinmetz@gmail.com. 

## Note about annotation volume
The original volume has numbers that correspond to the "id" field in the structure tree, but since I wanted to make a colormap for these, I re-indexed the annotation volume by the row number of the structure tree. So in this version the values correspond to "index"+1. This also allows using uint16 datatype, cutting file size in half. See setup_utils.m.


# removePBC_break_in_multimeric_str
gmx_mpi trjconv -f step7.trr -s step7.tpr -o new1.trr -pbc whole 

gmx_mpi trjconv -f new1.trr -s step7.tpr -o new2.trr -pbc nojump 

gmx_mpi trjconv -f new2.trr -s step7.tpr -o new3.trr -pbc cluster -center yes 

gmx_mpi trjconv -f new3.trr -s step7.tpr -o new4.trr -pbc mol -center yes 

gmx_mpi trjconv -f new4.trr -s step7.tpr -o step7_noPBC.trr -pbc mol -ur compact -center -n index.ndx (delete prev noPBC, only SOLU) 

gmx_mpi trjconv -f step7.trr -s step7.tpr -o step6.6_solu.gro -pbc mol -ur compact -center -n index.ndx -dump 0 

 
 

*****now we made script remove_pbc.sh with echo option 

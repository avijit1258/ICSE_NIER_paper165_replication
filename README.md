## Install instruction
* copy the code 
    git clone https://github.com/avijit1258/ICSE_NIER_paper165_replication.git
* go inside the downloaded code
    cd ICSE_NIER_paper165_replication
* create Python virtual environment
    python3 -m venv virtual_env
* activate the virtual environment
    source virtual_env/bin/activate
* install required packages
    pip install -r requirements.txt
* run the app.py
    python3 app/app.py


## Generating new ACS tree

* If we want to generate ACS tree for a new subject system (for example, Detectron), we need to generate TGF file from the Python source code.
* The TGF file should go to the *dataset* folder. 
* To generate TGF file from Python code, we need to install pyan3 (https://github.com/Technologicat/pyan). 
    pyan3 /home/avijit/Detectron/detectron/**/*.py --uses --no-defines --colored --grouped --annotated  -f subject_system.txt --uses --no-defines --tgf
* pyan3 might cause some error depending on the Python version of the subject system. Please consult their GitHub repository for issues.
* Update the variables in config.py file. 
* Now, we need to run ClusteringCallGraph.py to generate the ACS tree at *output* directory. 
    python3 app/ClusteringCallGraph.py
* To visualize the ACS tree, run the app.py now. 
    python3 app/app.py



## Exploring the ACS tree

* visit https://hcpc.usask.ca to check out hosted application
* select subject system from left side of the panel
* click the Load ACS Tree button to load ACS tree of the selected subject system
* right click on the nodes to see their corresponding node summary, execution patterns and files related to that node
* select any function at *Highlight nodes with similar function* dropdown, the nodes in the ACS tree will be
highlighted for guided browsing

The recommended Python version is 3.8. 

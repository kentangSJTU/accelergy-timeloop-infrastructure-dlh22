Accelergy-Timeloop Infrastructure
---------------------------------------------------


Installation (Apr. 23, 2022 update)
---------------------------------------------------

Based on [here](http://accelergy.mit.edu/infra_instructions.html):

```bash
sudo apt install scons libconfig++-dev libboost-dev libboost-iostreams-dev libboost-serialization-dev libyaml-cpp-dev libncurses-dev libtinfo-dev libgpm-dev git build-essential python3-pip
git clone --recurse-submodules https://github.com/kentangSJTU/accelergy-timeloop-infrastructure-dlh22.git
cd accelergy-timeloop-infrastructure
make pull
cd src/cacti
make
cd ../accelergy
pip install .
cd ../accelergy-aladdin-plug-in/
pip install .
cd ../accelergy-cacti-plug-in/
pip3 install .
cp -r ../cacti ~/.local/share/accelergy/estimation_plug_ins/accelergy-cacti-plug-in/
cd ../accelergy-table-based-plug-ins/
pip install .
cd ../timeloop
cd src/
ln -s ../pat-public/src/pat .
cd ..
scons -j4 --accelergy --static
cp build/timeloop-* ~/.local/bin
```

After that, we can run 
```bash
export PATH=$PATH:~/.local/bin
```

or add this line of code to the `~/.bashrc` or `~/.zshrc` file of your machine. Notice that the timeloop repository is from [here](https://github.com/kentangSJTU/timeloop-dlh22).


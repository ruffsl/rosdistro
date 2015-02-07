FROM ubuntu:12.04

# Configure Ubuntu repositories
RUN apt-get update && apt-get install -y \
	software-properties-common \
	wget

# Setup sources.list and keys
RUN echo "deb http://packages.ros.org/ros/ubuntu precise main" > /etc/apt/sources.list.d/ros-latest.list \
	&& wget http://packages.ros.org/ros.key -O - | apt-key add -

# Install ROS
RUN apt-get update && apt-get install -y \
	ros-hydro-ros-base \
	python-rosinstall

# Setup rosdep and environment
RUN rosdep init \
	&& rosdep update \
	&& echo "source /opt/ros/hydro/setup.bash" >> ~/.bashrc

# Intall some basic CLI tools
RUN apt-get install -y \
	curl \
	screen \
	byobu \
	git \
	nano

CMD ["bash"]
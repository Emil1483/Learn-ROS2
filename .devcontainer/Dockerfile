FROM ros:humble

# Install dev tools
RUN apt-get update && apt-get install -y \
    python3-colcon-common-extensions \
    python3-rosdep \
    python3-pip \
    ros-humble-rclpy \
    ros-humble-rqt-graph \
    ros-humble-foxglove-bridge \
    && rm -rf /var/lib/apt/lists/* \
    && pip install poetry

ENV POETRY_VIRTUALENVS_IN_PROJECT=true
ENV POETRY_VIRTUALENVS_OPTIONS_SYSTEM_SITE_PACKAGES=true

# Source ROS2 on every bash session
RUN echo "source /opt/ros/humble/setup.bash" >> /root/.bashrc
RUN echo "source /repo_root/ros2_ws/install/setup.bash 2>/dev/null || true" >> /root/.bashrc
RUN echo "export PYTHONPATH=\$PYTHONPATH:/repo_root/ros2_ws/.venv/lib/python3.10/site-packages" >> /root/.bashrc

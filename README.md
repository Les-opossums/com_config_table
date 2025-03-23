# com_config_table
This yaml files are used to confgure ROS msg for the communication between the zynq and the Raspberry_file. 

There are three files for the configuration :
- **com_msgs.yaml** : This file is used to synchronize communication frames format between zynq and Ros. It will be used to generate c function for the communication in the zynq software project.
- **format_msgs.yaml** : This file is used to synchronize the format of data between zynq and Ros. It will be used to generate C structure directly in the zynq software project.
- **version.yaml** : This file is used to ensure that both zynq and raspberry configurations are compatible. 

## General rule:
- **com_msgs.yaml** : The name of each table is equal to the name of the command used as header of the communication. The only rule heare is to use caracters <strong>^[a-zA-Z]+$</strong>. The <em><strong>send</em></strong> or <em><strong>receive</em></strong> parameters are describing the behavior of the communication. 
    - <em><strong>send</em></strong> : type of parameters to send after header (ROS perspective)
    - <em><strong>receive</em></strong> : type of parameters to receive after header (ROS perspective)

- **format_msgs.yaml** : 
    - The <em><strong>struct</em></strong> parameter of the table is the format of the c struct with all parameters and their type.
    - The <em><strong>info</em></strong> parameter of the table is used to give :
        - The <em><strong>file</em></strong> in which the c code generator shall create the structure
        - The <em><strong>object</em></strong> as all variable of type struct to create in the file. Thys will be created as external parameters.






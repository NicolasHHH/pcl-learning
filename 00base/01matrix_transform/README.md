# 01 Matrix Transform 

### Difference between .ply and .pcd

- For a PLY-file, the pcwrite function converts an organized M-by-N-by-3 point cloud to an unorganized M-by-3 format. It converts the format because PLY files do not support organized point clouds. To preserve the organized format, you can save the point cloud as a PCD-file.
- PLY 不支持保存成有序点云格式，PCD 可以

### Read from command line args

    std::vector<int> filenames;
    filenames = pcl::console::parse_file_extension_argument(argc, argv, ".ply"); # .pcd

### Basic Data type

    pcl::PointCloud<pcl::PointXYZ>::Ptr source_cloud(new pcl::PointCloud<pcl::PointXYZ>());


### How transformation matrix works 

    Reminder: how transformation matrices work :

           |-------> This column is the translation
    | 1 0 0 x |  \
    | 0 1 0 y |   }-> The identity 3x3 matrix (no rotation) on the left
    | 0 0 1 z |  /
    | 0 0 0 1 |    -> We do not use this line (and it has to stay 0,0,0,1)


### Cloud transformation 

    Eigen::Matrix4f transform_1 = Eigen::Matrix4f::Identity();

    float theta = M_PI / 4; // The angle of rotation in radians
    transform_1(0, 0) = std::cos(theta);
    transform_1(0, 1) = -sin(theta);
    transform_1(1, 0) = sin(theta);
    transform_1(1, 1) = std::cos(theta);
    transform_1(0, 3) = 0.5; // translation x 

    Eigen::Affine3f transform_2 = Eigen::Affine3f::Identity();
    transform_2.translation() << 2.5, 0.0, 0.0;
    transform_2.rotate(Eigen::AngleAxisf(theta, Eigen::Vector3f::UnitZ()));
    std::cout << transform_2.matrix() << std::endl;

    pcl::transformPointCloud(*source_cloud, *transformed_cloud, transform_2);

### Visualisation


    pcl::visualization::PCLVisualizer viewer("Matrix transformation example");

    pcl::visualization::PointCloudColorHandlerCustom<pcl::PointXYZ> source_cloud_color_handler(source_cloud, 255, 255, 255);
    viewer.addPointCloud(source_cloud, source_cloud_color_handler, "original_cloud");

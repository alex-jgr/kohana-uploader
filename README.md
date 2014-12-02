kohana-uploader
===============

A Kohana Framework module for handling file uploads. It only works on images at the moment.

A configuration example is located in the config folder. Looks like this

return array(
    'some-image' => array(
        'path'  => DOCROOT . 'public/images/teams',
        'adapter'  => 'File_Image',
        'extensions' =>  array('jpg', 'jpeg', 'gif'),
        'versions' => array(
            'thumb' => array(
                'width'     => 64, 
                'height'    => 64,
                'crop'      => TRUE,
                'quality'   => 100,
                'crop_x'    => NULL,
                'crop_y'    => NULL
            ),
            'normal' => array(
                'width'     => 640,
                'height'    => 480,
                'crop'      => TRUE,
                'quality'   => 100,
                'crop_x'    => NULL,
                'crop_y'    => NULL
            )
        ),
        'keep-original' => FALSE
    ),
  )

Usage:
$uploader = Uploader::factory('some-image')->process_upload($_FILES['image']);

This code will look for the file type 'some-image' in the config file and will create save or create (or both) the new image returning an array which contains information on the resulting image or images.

If the original image is no longer needed, then set 'keep-original' to FALSE or don't mention it. If it is needed then it will have to be TRUE.

For each version specified in the 'versions' a new image will be created with the given attributes and placed into a folder composed by the value in the 'path' concatenated with the array key of the version.

Define as many image types as you need.

Any suggestions will be taken into consideration.
kohana-uploader
===============

A Kohana Framework module for handling file uploads. It only works on images at the moment.

A configuration example is located in the config folder.

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

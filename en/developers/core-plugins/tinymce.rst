TinyMCE
#######

.. versionchanged:: 1.5.1
    TinyMCE is not included out of the box in 1.5.1.  Ckeditor has been
    is now is the default RTE.

TinyMCE is a popular WYSIWYG editor by Moxiecode Systems. It is packaged and shipped as a plugin with Croogo.

By default, the editor loads when you add/edit Nodes in your admin panel. To load it in other places and take more control of it's settings, see configuration information below.

Configuration
=============

Configuration for this at `/app/Plugin/Tinymce/Config/bootstrap.php` looks like this::

    Configure::write('Tinymce.actions', array(
        'Nodes/admin_add' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
        'Nodes/admin_edit' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
        'Translate/admin_edit' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
    ));

For example, if you wanted to load the editor in your Products controller's add method for Product model's body field, add this line in the end::

    Configure::write('Tinymce.actions', array(
        'Nodes/admin_add' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
        'Nodes/admin_edit' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
        'Translate/admin_edit' => array(
            array(
                'elements' => 'NodeBody',
            ),
        ),
        'Products/add' => array(
            array(
                'elements' => 'ProductBody',
            ),
        ),
    ));
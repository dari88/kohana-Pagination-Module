Very convenient Pagination Module for kohana 3.2
================================================

V2.0 (2012/07/15)
--------------------

- Except the name of the core PHP, camelCase has been discontinued. Underbar(_) has been used for separation of terms.
- Fixed the case that the item is empty.

This VPM is codes modification of Zend Paginator. It's input is Database_MySQL_Result, output is paginator and rendered view of pagination. It's very convenient!

Most simple usage:
------------------
    // Model
    $select = DB::select('*')
    return $select->execute();
    
    // Controller
    $model = Model::factory('test12_posts');
    $select = $model->selectblogs($array);
    $paginator = Paginator::factory($select);
    $paginator->set_Current_Page_Number($page);
    $view = View::factory('test12/edit/posts');
    $view->data = $paginator;
    $view->pagination = $paginator->render();
    
    // View
    <?PHP
           foreach ($data as $d) {
               echo $d['post_title'];
           }
           echo $pagination;
    ?>

Options for example:
--------------------
    $paginator->set_Option_Queries('http://example.com/kohana', 'PageNumber', 'option=draft');
    $paginator->set_Item_Count_Per_Page(30);  // Default = 10
    $paginator->render('Elastic');  // Scrolling style
    $pagecount = $paginator->count();

Install:
--------
* Download and copy paginator folder under kohana/modules/ folder.
* Edit your bootstrap.php file and add next line.
* `'paginator'  => MODPATH.'paginator',`

View file can be modified:
--------------------------
1. Copy `modules/paginator/views/paginator/pagination.php` under `application/views/paginator/` folder.
2. Modify it as you like.



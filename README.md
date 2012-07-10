Very convenient Pagination Module for kohana 3.2
================================================

This VPM is codes modification of Zend Paginator. It's input is Database_MySQL_Result, and output is renderd view of pagination. It's very convenient!

Most simple usage:
------------------
    // Model
    $select = DB::select('*')
    return $select->execute();
    
    // Controller
    $model = Model::factory('test12_posts');
    $select = $model->selectblogs($array);
    $paginator = Paginator::factory($select);
    $paginator->setCurrentPageNumber($page);
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
    $paginator->setOptionQueries('http://example.com/kohana', 'PageNumber', 'option=draft');
    $paginator->setItemCountPerPage(30);  // Default = 10
    $paginator->render('Elastic');  // Scrolling style
    $pagecount = $paginator->count();

Install:
--------
* Dounload and set paginator folder under kohana/modules/ folder.
* Edit your bootstrap.php file and add next line.
* `'paginator'  => MODPATH.'paginator',`

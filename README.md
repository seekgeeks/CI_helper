# CI : Codeigniter helper model
 Codeigfniter version 3.x
 PHP version 5.5+

 Author Dheeraj Thedijje
 Thedijje.com
 File is free to use and download
 this includes codeigniter universal helper files

 ## What is CI helper for?
 Codeigniter is no doubt really great framework to get your work done with less and less mess. All you have to do is focus on your App and don't re-invent wheel.
 However 
 While working with CI, i felt lots of thing while writing model, i need to repeat again and again
 For example
 ```
 public function some_model(){
		$this->db->from('table_name');
		$this->db->where(array('col'=>'desire_value'));
		$this->db->limit(10);
		$query	=	$this->db->get();
		return $query->result();
 }
 
 ```

 In code written above, all we needed to change was
 - 'table_name'
 - 'where' condition array
 - 'limit' count

 but i had to write code again and again. so what i did here is this.
 ```
 public function get_multiple($table,$condition=NULL,$limit=10){
		$this->db->from($table);
		$this->db->where($condition);
		$this->db->limit($limit);
		$query	=	$this->db->get();
		return $query->result();
 }
 ```

 Now all i have to do is for any table any query, i never had to write this code again and again. just use that as follows

 ```
 $users_list	=	$this->helper_mode->get_multiple('users',array('status'=>1),10);

 ```

 I am done, yes its great!!
 ## Getting started

 ### Cloning or Downloading package
 You can start fresh project via just cloning our git repo into your development environment
 Just do 
 ```
 $ git clone https://github.com/Thedijje/CI_helper.git
 
 ```

 ### Configuring
 You really don't have to digg inside to configure anything, most of settings are pre-configured. You can configure _database_ and _base url_ values right in index.php file, Yeah.. I know its Awesome


### Functions list
Following are the functions inside **helper_model** of this package

| Sr | Function Name | Use syntax | Comment  |
|----|---------------|------------|----------|
|	1	|	get_settings	|	$this->lib->get_settings('sitename')	|	Please refer detail of this function below	|
|	2	|	upload_file		|	$this->lib->upload_file($path,$name)		|	path is directory where file to be save, $name is input field name of file, use for single file upload only	|
|	3	|	display_alert	|	$this->lib->display_alert($msg,$type,$icon)	|	Show formatted display message in bootstrap alert style 	|
|	4	|	redirect_msg	|	$this->lib->redirect_msg($msg,$type,$url)	|	Show message on next page after redirect, e.g. Record deleted successfully	|
	


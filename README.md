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
 $users_list	=	$this->helper_model->get_multiple('users',array('status'=>1),10);

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

#### General functions 

| Sr | Function Name | Use syntax | Comment  |
|----|---------------|------------|----------|
|	1	|	get_settings	|	$this->lib->get_settings('sitename')	|	Please refer detail of this function below	|
|	2	|	upload_file		|	$this->lib->upload_file($path,$name)		|	path is directory where file to be save, $name is input field name of file, use for single file upload only	|
|	3	|	display_alert	|	$this->lib->display_alert($msg,$type,$icon)	|	Show formatted display message in bootstrap alert style 	|
|	4	|	redirect_msg	|	$this->lib->redirect_msg($msg,$type,$url)	|	Show message on next page after redirect, e.g. Record deleted successfully	|
|	5	|	alert_message	|	$this->lib->alert_message()	|	Put this code on html code where output of redirect_msg function is to display_alert|
|	6	|	send_formatted_mail	|	$this->lib->send_formatted_mail($data)	|	View detail of this function for usecase	|
|	7	|	image_resize	|	$this->lib->image_resize($path,$width,$height)	|	Resize any valid image file using this simple Function 	|
|	8	|	update_sitedata	|	$this->lib->update_sitedata($var,$val)	|	Update table used in get_setting to update data in it 	|


#### Database functions

|	Sr	|	Function Name	|	Use syntax	|	Comment	|
|----|---------------|------------|----------|
|	1	|	del 	|	$this->lib->del($table,$col,$val)	|	Delete a record in table using table name, col and value 	|
|	2	|	update 	|	$this->lib->update($table,$data,$col,$val)	|	Update table set dataset where $col is havin $value |
|	3	|	get_by_id	|	$this->lib->get_by_id($table,$col,$val,$limit,$order)	|	Get multiple record by providing single where condition, optionally can sort and linmit the output desire_value|
|	4	|	get_multi_where	|	$this->lib->get_multi_where($table,$conditions,$limit,$count,$order,$group)	|	Get Multiple values by providing multiple condition, optionally can sort, order,get only count of result and group data accordingly	|
|	5	|	get_row_array	|	$this->lib->get_row_array($table,$where,$order,$limit)	|	get single record using multiple condition, order and linmit 	|
|	6	|	get_row 	|	$this->lib->get_row($table,$col,$val,$col_get)	| Get single row in array form if specified col, get single value based on conditions 	|
|	7	|	get_table	|	$this->lib->get_table($table,$order,$group,$limit)	|	Get table, additionally apply multiple sorting, grouping, and limit 	|
|	8	|	count_data	|	$this->lib->count_data($table,$col,$val)	|	Quickly Get num row value based on condition on table 	|
|	9	|	 count_multiple	|	$this->lib->count_multiple($table,$condition)	|	Get num row of table or condition on it 	|
| 10	|	search	|	$this->lib->search($table,$query_text,$attributes)	|	Search from table using query and list of col to search for 	|



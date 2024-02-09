```javascript
//Ajax Load Data Code
 $(document).ready(function() {
            function loadTable() {
                $.ajax({
                    url: "ajax-load.php",
                    type: "POST",
                    success: function(data) {
                        $('#table-data').html(data);
                    }
                });
            }
            loadTable();
//Ajax Insert Data
            $("#Submit").on("click", function(e) {
                e.preventDefault();
                var fname = $("#f_name").val();
                var lname = $("#l_name").val();
                if (fname.trim() === "" || lname.trim() === "") {
                    alert("Please enter both first and last names.");
                    return;
                }
                $.ajax({
                    url: "Ajax-insert.php",
                    type: "POST",
                    data: {
                        first_name: fname,
                        last_name: lname
                    },
                    success: function(data) {
                        if (data == 1) {
                            loadTable();
                            $("#myForm").trigger("reset");
                        } else {
                            alert("Can't save Record.");
                        }
                    }
                });

            });
//Ajax Delete
            $(document).on("click",".delete-btn",function(){
                var studentId=$(this).data("id");
                var element=this;
                $.ajax({
                    url:"Ajax-Delete.php",
                    type:"POST",
                    data:{id:studentId},
                    success:function(data){
                        if(data==1){
                            $(element).closest("tr").fadeOut();
                        }else{
                         
                        }
                    }
                })
            })
        });
```
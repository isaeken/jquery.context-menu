# jQuery Context Menu
![jQuery Context Menu](https://i.imgyukle.com/2020/05/11/reOHzy.png)

## Usage

### with html

    <div class="context-menu-trigger">  
	    <ul class="context-menu-content">  
	        <li>  
	            <a href="https://www.isaeken.com.tr">  
	                This is a link!  
	            </a>  
	        </li>  
	        <li>  
	            <a onclick="alert('Testing...')">  
	                JavaScript!  
	            </a>  
	        </li>  
	    </ul>  
	    Left click here  
    </div>

### with javascript

  

    <div id="element"></div>
    <script>
    var contextMenu = $('#element').contextMenu();
    contextMenu.button = mouseButton.LEFT;
    contextMenu.menu().addItem('This is <b>first</b> item!');
    contextMenu.menu().addItem('<b>Item</b> content', 'https://www.isaeken.com.tr');
    contextMenu.menu().addItem('This is <u>Third</u> item', function () {  
	    alert('Hello world!');  
	});
	contextMenu.menu().addItem('<span class="material-icons">bookmark</span>Item with Material Icon');
	contextMenu.menu().addItem('<i class="fab fa-npm"></i>Item with Font Awesome');
	contextMenu.menu().addItem('Click to delete me!', function () {  
	    contextMenu.menu().removeItem(5);
    });
    contextMenu.menu().addItem('Change trigger: <b>Mouse LEFT</b>', function () {  
	    contextMenu.button = mouseButton.LEFT;  
	    contextMenu.update();  
	});
	contextMenu.menu().addItem('Change trigger: <b>Mouse MIDDLE</b>', function () {  
	    contextMenu.button = mouseButton.MIDDLE;  
	    contextMenu.update();  
	});  
	contextMenu.menu().addItem('Change trigger: <b>Mouse RIGHT</b>', function () {  
	    contextMenu.button = mouseButton.RIGHT;  
	    contextMenu.update();  
	});
	contextMenu.menu().addItem('onclick event', function () {  
	    contextMenu.onclick = function () {  
	        $('#log').append('You are clicked!<br>');  
	        this.close();  
	    }
	});
	contextMenu.menu().addItem('onopen event', function () {  
	    contextMenu.onopen = function () {  
	        $('#log').append('Context menu opened!<br>');  
	    }  
	});
	contextMenu.init();
    </script>

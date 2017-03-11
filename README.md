::HTML::
==========================================
    <div id="sb-search" class="sb-search " >
        <form>
            <input class="sb-search-input " onkeyup="buttonUp();" placeholder="Enter your search term..." onblur="monkey();" type="search" value="" name="search" id="search">
            <input class="sb-search-submit" type="submit"  value="">
            <span class="sb-icon-search"><i class="fa fa-search"></i></span>
        </form>
    </div>

::CSS::
=========================================
		.sb-search {
        position: relative;
        margin-top: 10px;
        width: 0%;
        min-width: 60px;
        height: 60px;
        float: right;
        overflow: hidden;
        -webkit-transition: width 0.3s;
        -moz-transition: width 0.3s;
        transition: width 0.3s;
        -webkit-backface-visibility: hidden;
		}

		.sb-search-input {
        position: absolute;
        top: 0;
        right: 0px;
        border: none;
        outline: none;
        background: #fff;
        width: 100%;
        height: 60px;
        margin: 0;
        z-index: 10;
        padding: 20px 65px 20px 20px;
        font-family: inherit;
        font-size: 20px;
        color: #2c3e50;
		}
		 
		input[type="search"].sb-search-input {
        -webkit-appearance: none;
        -webkit-border-radius: 0px;
		}
		.sb-search-input::-webkit-input-placeholder {
			  color: #efb480;
		}
		 
		.sb-search-input:-moz-placeholder {
			  color: #efb480;
		}
		 
		.sb-search-input::-moz-placeholder {
			  color: #efb480;
		}
		 
		.sb-search-input:-ms-input-placeholder {
			  color: #efb480;
		}

		.sb-icon-search,
		.sb-search-submit  {
        width: 60px;
        height: 60px;
        display: block;
        position: absolute;
        right: 0;
        top: 0;
        padding: 0;
        margin: 0;
        line-height: 60px;
        text-align: center;
        cursor: pointer;
		}

		.sb-search-submit {
        background: #fff; /* IE needs this */
        -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=0)"; /* IE 8 */
        filter: alpha(opacity=0); /* IE 5-7 */
        opacity: 0;
        color: transparent;
        color:red;
        border: none;
        outline: none;
        z-index: -1;
		}

		.sb-icon-search {
        color: #fff;
        background: #e67e22;
        z-index: 90;
        font-size: 22px;
        font-family: 'icomoon';
        speak: none;
        font-style: normal;
        font-weight: normal;
        font-variant: normal;
        text-transform: none;
        -webkit-font-smoothing: antialiased;
		}
		 
		.sb-icon-search:before {
			  content: "";
		}

		.sb-search.sb-search-open,
		.no-js .sb-search {
			  width: 100%;
		}

		.sb-search.sb-search-open .sb-icon-search,
		.no-js .sb-search .sb-icon-search {
        background: #da6d0d;
        color: #fff;
        z-index: 11;
		}

		.sb-search.sb-search-open .sb-search-submit,
		.no-js .sb-search .sb-search-submit {
        z-index: 90;
    }
::JavaScript/jQuery:: (Add jquery library)
=========================================
    function buttonUp(){
         var valux = $('.sb-search-input').val(); 
            valux = $.trim(valux).length;
            if(valux !== 0){
                $('.sb-search-submit').css('z-index','99');
            } else{
                $('.sb-search-input').val(''); 
                $('.sb-search-submit').css('z-index','-999');
            }
    }
    
    $(document).ready(function(){
        var submitIcon = $('.sb-icon-search');
        var submitInput = $('.sb-search-input');
        var searchBox = $('.sb-search');
        var isOpen = false;
        
        $(document).mouseup(function(){
            if(isOpen == true){
            submitInput.val('');
            $('.sb-search-submit').css('z-index','-999');
            submitIcon.click();
            }
        });
        
        submitIcon.mouseup(function(){
            return false;
        });
        
        searchBox.mouseup(function(){
            return false;
        });
                
        submitIcon.click(function(){
            if(isOpen == false){
                searchBox.addClass('sb-search-open');
                isOpen = true;
            } else {
                searchBox.removeClass('sb-search-open');
                isOpen = false;
            }
    });

});	
==========================================

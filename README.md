$ ( tài liệu ) . sẵn sàng ( function ( )  {
    // thanh xử lý
    setTimeout ( function ( )  {
        firstQuestion ( ) ;
        $ ( '.spinner' ) . phaiOut ( ) ;
        $ ( '#preloader' ) . trì hoãn ( 350 ) . fadeOut ( 'chậm' ) ;
        $ ( 'body' ) . trì hoãn ( 350 ) . css ( {
            'tràn' : 'hiển thị'
        } ) ;
    } ,  600 ) ;
} )

function  firstQuestion ( ) {
    
    $ ( '.content' ) . ẩn ( ) ;
    Swal . lửa ( {
        title : 'Anh ấy luu cậu!' ,
        text : 'Tôi có điều này muốn hỏi cậu nhớ phải trả lời thật lòng nhaaa.' ,
        imageUrl : 'img / cuteCat.jpg' ,
        imageWidth : 300 ,
        imageHeight : 300 ,
        background : '#fff url ("img / iput-bg.jpg")' ,
        imageAlt : 'Hình ảnh tùy chỉnh' ,
      } ) . then ( function ( ) {
        $ ( '.content' ) . show hàng ( 200 ) ;
      } )
}

 // chuyển đổi vị trí nút
 function  switchButton ( )  {
    var  audio  =  new  Audio ( 'sound / duck.mp3' ) ;
    âm thanh . chơi ( ) ;
    var  leftNo  =  $ ( '#no' ) . css ( "trái" ) ;
    var  topNO  =  $ ( '#no' ) . css ( "đầu trang" ) ;
    var  leftY  =  $ ( '#yes' ) . css ( "trái" ) ;
    var  topY  =  $ ( '#yes' ) . css ( "đầu trang" ) ;
    $ ( '# không' ) . css ( "left" ,  leftY ) ;
    $ ( '# không' ) . css ( "top" ,  topY ) ;
    $ ( '#yes' ) . css ( "left" ,  leftNo ) ;
    $ ( '#yes' ) . css ( "top" ,  topNO ) ;
}
// di chuyển nút ngẫu nhiên póition
function  moveButton ( )  {
    var  audio  =  new  Audio ( 'sound / Swish1.mp3' ) ;
    âm thanh . chơi ( ) ;
    if  ( screen . width <= 600 )  {
        var  x  =  Toán học . ngẫu nhiên ( )  *  300 ;
        var  y  =  Toán học . ngẫu nhiên ( )  *  500 ;
    }  khác {
        var  x  =  Toán học . ngẫu nhiên ( )  *  500 ;
        var  y  =  Toán học . ngẫu nhiên ( )  *  500 ;
    }
    var  left  =  x  +  'px' ;
    var  top  =  y  +  'px' ;
    $ ( '# không' ) . css ( "trái" ,  trái ) ;
    $ ( '# không' ) . css ( "đầu trang" ,  đầu trang ) ;
}


var  n  =  0 ;
$ ( '# không' ) . mousemove ( function ( )  {
    nếu  ( n  <  1 )
        switchButton ( ) ;
    nếu  ( n  >  1 )
        moveButton ( ) ;
    n ++ ;
} ) ;
$ ( '# không' ) . nhấp vào ( ( )  =>  {
    if  ( màn hình . chiều rộng > = 900 )
        switchButton ( ) ;
} )

// tạo văn bản trong đầu vào
function  textGenerate ( )  {
    var  n  =  "" ;
    var  text  =  "Tại vì cậu đẹp trai vl: <<<<<<<" ;
    var  a  =  Mảng . from ( văn bản ) ;
    var  textVal  =  $ ( '#txtReason' ) . val ( ) ? $ ( '#txtReason' ) . val ( ) : "" ;
    var  count  =  textVal . chiều dài ;
    nếu  ( đếm  >  0 )  {
        for  ( cho  i  =  1 ;  i  <=  count ;  i ++ )  {
            n  =  n  +  a [ i ] ;
            if  ( i  ==  text . length  +  1 )  {
                $ ( '#txtReason' ) . val ( "" ) ;
                n  =  "" ;
                phá vỡ ;
            }
        }
    }
    $ ( '#txtReason' ) . val ( n ) ;
    setTimeout ( "textGenerate ()" ,  1 ) ;
}

// hiển thị cửa sổ bật lên
$ ( '#yes' ) . nhấp vào ( function ( )  {
    var  audio  =  new  Audio ( 'sound / tick.mp3' ) ;
    âm thanh . chơi ( ) ;
    Swal . lửa ( {
        title : 'Nói cho tớ lí do cậu thích tớ đi: vvvv' ,
        html : true ,
        chiều rộng : 900 ,
        padding : '3em' ,
        html : "<input type = 'text' class = 'form-control' id = 'txtReason' onmousemove = textGenerate () placeholder = 'Whyyy'>" ,
        background : '#fff url ("img / iput-bg.jpg")' ,
        phông nền : `
              rgba (0,0,123,0,4)
              url ("img / giphy2.gif")
              trên bên trái
              không lặp lại
            ` ,
        showCancelButton : true ,
        hủy bỏButtonText : "Thôi ngại lém: <<" ,
        confirmButtonColor : '# 3085d6' ,
        hủy bỏButtonColor : '# d33' ,
        confirmButtonColor : '# fe8a71' ,
        hủy bỏButtonColor : '# f6cd61' ,
        verifyButtonText : 'Gửi cho tớ <3'
    } ) . then ( ( kết quả )  =>  {
        if  ( kết quả . giá trị )  {
            Swal . lửa ( {
                chiều rộng : 900 ,
                confirmButtonText : 'Okiiiii lun <3' ,
                background : '#fff url ("img / iput-bg.jpg")' ,
                title : 'Tớ biết mà ^^ Yêu cậu 300.000' ,
                text : "Tối nay tớ qua đón cậu đi chơi nhaaaaaaaaa: v Còn giờ thì đợi gì nữa mà ko inbox cho tớ đi nàoooooo" ,
                confirmButtonColor : '# 83d0c9' ,
                onClose : ( )  =>  {
                    cửa sổ . location  =  'http://fb.com' ;
                  }
            } )
        }
    } )
} )

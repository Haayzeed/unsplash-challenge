<template>
    <div>
        <input type="checkbox" id="sidebar-toggle">
        <div class="sidebar">
            <div class="sidebar-brand">
                <div class="brand-flex">
                    <img src="@/assets/img.png" width="40px" alt="">
                </div>
            </div>
            <div class="sidebar-main">
                <div class="sidebar-menu">
                    <ul>
                        <li class="active"><a href=""><span class="fas fa-home"></span> Dashboard</a></li>
                        <li><a href=""><span class="fas fa-file"></span> Message</a></li>
                        <li><a href=""><span class="fas fa-chart-bar"></span> Ranking</a></li>
                        <li><a href=""><span class="fas fa-chess-queen"></span> Challenge</a></li>
                        <li><a href=""><span class="fas fa-filter"></span> Party</a></li>
                        <li><a href=""><span class="fas fa-link"></span> Connect</a></li>
                        <li><a href=""><span class="fas fa-male"></span> Parade</a></li>
                        <li><a href=""><span class="fas fa-users"></span> Group</a></li>                        
                    </ul>
                </div>
            </div>
        </div>
        <label for="sidebar-toggle" class="body-label"></label>
    </div>
</template>

<style lang="scss">
    :root{
        --light-gray: rgb(250, 250, 252);
    }
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    body{
        background: var(--light-color);
        font-family: 'Poppins', sans-serif;
    }
    #sidebar-toggle{
    display: none;
    &:checked ~ .sidebar{
        left: -100%;
        @media (max-width: 1124px){
            left: 0;
        }
    }
    &:checked ~ .body-label{
        right: 0%;
    }
}
.body-label{
    position: fixed;
    width: calc(100% - 280px);
    height: 100%;
    z-index: 30;
    right: -100%;   
    top: 0;
}
.sidebar{
    width: 280px;
    position: fixed;
    left: 0;
    top: 0;
    height: 100%;
    padding: 1rem 1.5rem;
    background: var(--light-gray);
    color: #000;
    border-right: 1px solid #ccc; 
    z-index: 20;
    transition: left 300ms;
    @media (max-width: 1124px){
        left: -100%;
        z-index: 30;
    }
    &-brand{
        height: 70px;
    }
    .brand-flex{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    &-main{
        ul{
            list-style-type: none;
            margin-bottom: 1.5rem;
            li{
                margin-bottom: .3rem;
                padding: 10px;
                cursor: pointer;
                &.active, &:hover{
                    border: 1px solid #ccc;
                    border-radius: 5px;
                    a{
                        color: #000;
                        span{
                            color: rgb(107,97,186);
                        }
                    }
                }
                a{
                    color: rgb(194,193,199);
                    font-size: 14px;
                    display: flex;
                    align-items: center;
                    text-decoration: none;
                    span{
                        font-size: 20px;
                        margin-right: .8rem;
                    }
                }
            }
        }
    }
}
header{
    height: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2.5rem 1rem 1.5rem;
    background: var(--light-gray);
    position: fixed;
    top: 0;
    left: 280px;
    width: calc(100% - 280px);
    z-index: 20;
    @media (max-width: 1124px){
        left: 0%;
        width: 100%;
    }
    .menu-toggle{
        @media (min-width: 1124px){
            display: none;
        }
        label{ 
            width: 48px;
            height: 48px;
            font-size: 1.2rem;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 50%;
            &:hover{
                background: #efefef;
            }
        }
    }
    .input-box{
        width: 80%;
        position: relative;

        input{
            width: 100%;
            height: 40px;
            padding: 14px;
            outline: none;
            border: none;
            box-shadow: 4px 4px 10px rgba(0,0,0,0.1);
        }
        button{
            position: absolute;
            top: 5px;
            right: 5px;
            padding: 8px;
            border: none;
            outline: none;
            background:  rgb(107,97,186);
            color: #fff;
            border-radius: 3px;
        }
    }
    .header-icons{
        display: flex;
        align-items: center;
        span{
            display: inline-block;
            margin-left: 1rem;
            font-size: 16px;
        }
        .avatar{
            width: 30px;
            height: 30px;
            border-radius: 50%;
        }
    }
}
</style>
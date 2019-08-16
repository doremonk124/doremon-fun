<template>
    <div class="container">
        <div class="text-center" style="margin: 80px"><h1>Đấu trường sinh tử</h1></div>
        <div class="row">
            <div class="col-md-12">
                <div class="row">
                    <div class="col-md-1"></div>
                    <div class="col-md-3 ys_lane">
                        <div class="position-relative">
                            <div class="position-relative" style="height: 255px">
                                <div class="chibi"></div>
                                <img class="chi_bi" src="~/static/image/yasuo.png" width="100%" alt="">
                                <img class="chi_bi_2 d-none position-absolute" src="~/static/image/action-ys.jpg" width="100%" height="255px" alt="" style="transition: all 1s;">
                            </div>
                            <div class="position-absolute d-none win_1" style="top:10px; left: -28px; padding: 10px; border: solid 2px; border-radius: 15px">Lêu lêu</div>
                            <div class="position-absolute d-none loser_1" style="top:20px; left: 230px; padding: 10px; border: solid 2px; border-radius: 15px">Auuu...</div>
                            <div class="position-absolute d-none end_1" style="top:20px; left: -58px; padding: 10px; border: solid 2px; border-radius: 15px">Kết thúc rồi</div>
                            <div class="position-absolute d-none end_2" style="top:20px; left: -58px; padding: 10px; border: solid 2px; border-radius: 15px">Thật đáng tiếc</div>
                        </div>
                        <div class="text-center"><b>You</b></div>
                        <div class="col-md-12" style="height: 30px"><div style="height:100%;background-color: green; width: 100%"></div></div>
                    </div>
                    <div class="col-md-4"></div>
                    <div class="col-md-3 zed_lane">
                        <div class="position-relative">
                            <div class="position-relative" style="height: 255px">
                                <div class="chibi"></div>
                                <img class="chi_bi" src="~/static/image/zed.jpg" width="100%" alt="">
                                <img class="chi_bi_2 d-none position-absolute" src="~/static/image/action-zed.png" width="100%" height="255px" alt="" style="transition: all 1s;">
                            </div>
                            <div class="position-absolute d-none loser_1" style="top:10px; left: -28px; padding: 10px; border: solid 2px; border-radius: 15px">Thấy sức mạnh của ta chưa</div>
                            <div class="position-absolute d-none win_1" style="top:20px; left: 270px; padding: 10px; border: solid 2px; border-radius: 15px">Khá khen cho mi</div>
                            <div class="position-absolute d-none end_1" style="top:20px; left: -58px; padding: 10px; border: solid 2px; border-radius: 15px">Ta sẽ trở lại</div>
                            <div class="position-absolute d-none end_2" style="top:20px; left: -58px; padding: 10px; border: solid 2px; border-radius: 15px">M k thoát được đâu con trai</div>
                        </div>
                        <div class="text-center"><b>Boss</b></div>
                        <div class="col-md-12" style="height: 30px"><div style="height: 100%;background-color: green; width: 100%"></div></div>
                    </div>
                    <div class="col-md-1"></div>
                </div>
            </div>
            <div style="margin: 0 auto"><button class="btn btn-success">Bắt đầu</button></div>
            <div style="margin: 0 auto"><button class="btn btn-primary">Bắt đầu</button></div>
        </div>
    </div>
</template>

<script>
    import Logo from '~/components/Logo.vue'

    export default {
        components: {
            Logo
        }
    }
    $(document).ready(function () {
        var chibi_ys = setInterval(function () {
            setTimeout(function () {
                $('.ys_lane .chibi').css('height', '0');
                $('.ys_lane .chi_bi').css('height', '255px');
                $('.ys_lane .chi_bi').css('transition', 'height 1.5s');
                $('.ys_lane .chibi').css('transition', 'height 1.5s');
            }, 1500);
            $('.ys_lane .chibi').css('height', '20px');
            $('.ys_lane .chi_bi').css('height', '235px');
            $('.ys_lane .chi_bi').css('transition', 'height 1.5s');
            $('.ys_lane .chibi').css('transition', 'height 1.5s');
        }, 3000);
        var chibi_zed = setInterval(function () {
            setTimeout(function () {
                $('.zed_lane .chibi').css('height', '0');
                $('.zed_lane .chi_bi').css('height', '255px');
                $('.zed_lane .chi_bi').css('transition', 'height 1.5s');
                $('.zed_lane .chibi').css('transition', 'height 1.5s');
            }, 1500);
            $('.zed_lane .chibi').css('height', '20px');
            $('.zed_lane .chi_bi').css('height', '235px');
            $('.zed_lane .chi_bi').css('transition', 'height 1.5s');
            $('.zed_lane .chibi').css('transition', 'height 1.5s');
        }, 3000);
        $(".btn-success").on('click', function () {
            // $(".btn-success").css('display', 'none');
            // $(".question_1").removeClass('d-none');
            $('.ys_lane .chi_bi').addClass('d-none');
            $('.ys_lane .chi_bi').css('height', '0');
            $('.ys_lane .chibi').css('height', '255px');
            clearInterval(chibi_ys);
            $('.ys_lane .chi_bi_2').css('top', '0');
            $('.ys_lane .chi_bi_2').removeClass('d-none');
            setTimeout(function () {
                $('.ys_lane .chi_bi_2').css('top', '-170px');
            }, 1000);
        });
        $(".btn-primary").on('click', function () {
            clearInterval(chibi_zed);
            $('.zed_lane .chi_bi').addClass('position-absolute');
            $('.zed_lane .chi_bi').css('top', '0');
            setTimeout(function () {
                $('.zed_lane .chi_bi').css('transition', 'all 1.5s');
                $('.zed_lane .chi_bi').css('top', '-170px');
            }, 500);
            setTimeout(function () {
                $('.zed_lane .chi_bi_2').css('top', '-170px');
                $('.zed_lane .chi_bi').addClass('d-none');
                $('.zed_lane .chi_bi_2').removeClass('d-none');
            }, 1800);
            // $('.zed_lane .chi_bi').addClass('d-none');
            // $('.zed_lane .chi_bi').css('height', '0');
            // $('.zed_lane .chibi').css('height', '255px');
            // clearInterval(chibi_zed);
            // $('.zed_lane .chi_bi_2').css('top', '0');
            // $('.zed_lane .chi_bi_2').removeClass('d-none');
            // setTimeout(function () {
            //     $('.zed_lane .chi_bi_2').css('top', '-170px');
            // }, 1000);
        });
    });
</script>
<template>
    <div class="bg-gray-800 min-h-screen h-cover w-cover bg-cover p-[50px]">
        <div class="fixed left-[-225px] top-[-50px]">
            <img src="../assets/images/rocket-use.png" alt="">
        </div>
        <div class="fixed right-[50px] bottom-[30px] max-h-[300px]">
            <img src="../assets/images/planet.png" alt="" class="h-[100px]">
        </div>
        <div class="flex-col justify-center">
            <div class="text-center flex justify-center h-[15px]">
                <h1 class="text-white text-[60px] w-[280px]">{ C N O }</h1>
            </div>
            <div class="p-[50px] flex flex-wrap justify-center mt-[10%]">
                    <div :class="getMemberNumber()" v-for="member in members" :key="member">
                        <button @click="showPopup(member.name);this.name=member.name;this.nickname=member.nickname;this.detail=member.detail;" class="h-cover w-cover">
                            <profileCard
                            :name = "member.name"
                            :nickname = "member.nickname"
                            :inGameName = "member.inGameName"
                            :team = "member.team"
                            :year = "member.year"
                            :birthday = "member.birthday"
                            :image = "member.image"
                            :facebook = "member.facebook"
                            :github = "member.github"
                            :instagram = "member.instagram"
                            >
                            </profileCard> 
                        </button>
                    </div>
            </div>
            <div v-if="selected" ref="detailBox" class="bg-gray-900 h-cover w-[30%] ml-[35%] pb-[12px] rounded-xl animate-popup font-code font-regular">
                <div class="bg-gray-300 pt-[1.5%] pl-[1.5%] pb-[1%] rounded-t-xl">
                    <div class="flex">
                        <div class="h-[10px] w-[10px] rounded-full bg-green-600 mr-[4px]"></div>
                        <div class="h-[10px] w-[10px] rounded-full bg-yellow-600 mr-[4px]"></div>
                        <div class="h-[10px] w-[10px] rounded-full bg-red-600 mr-[4px]"></div>
                    </div>
                </div>
                <div class="animate-fade">
                    <div class="text-red-300 ml-[3%] pt-[2%]">
                        <p class="text-fuchsia-500 inline">import </p>{{nickname}} <p class="text-fuchsia-500 inline"> from </p>"{{name}}"
                    </div>
                    <div class="text-blue-300 ml-[3%] pt-[2%] mr-[3%]">main : <p class="text-yellow-500">{</p></div>
                    <div class="text-gray-400 ml-[35px] mr-[35px]">{{detail}}</div>
                    <div class="text-yellow-500 ml-[3%]">}<span class="text-white">,</span></div>
                </div>
                
            </div>
        </div>
        
        
            <!-- <div class="basis-1/3">
                <profileCard
                    name = "Sittipong Hemloum"
                    nickname = "Ong"
                    inGameName = "KanaMooKrob"
                    team = "CNO"
                    year = "KU81"
                    birthday = "09-21-2001"
                    image = "https://scontent-sin6-2.xx.fbcdn.net/v/t1.15752-9/310835510_684981289522964_3461760171192846605_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=ae9488&_nc_ohc=RbRFs_Ahn1wAX8KvYaR&_nc_ht=scontent-sin6-2.xx&oh=03_AdQtCRMXZcFGk2BujrCs4TT0Z-x4cp8bb_OiUzy9xMIJEA&oe=6393DCA4"
                    >
                </profileCard>
            </div>
            <div class="basis-1/3">
                <profileCard
                    name = "Punnatad Duengkae"
                    nickname = "Nokkok"
                    inGameName = "DraftMaster"
                    team = "CNO"
                    year = "KU81"
                    birthday = "12-27-2002"
                    image = "https://scontent-sin6-3.xx.fbcdn.net/v/t1.15752-9/313894314_664603271857321_204835522882551428_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=ae9488&_nc_ohc=g_nLz-GHp5IAX8DLPcP&tn=9Fdpok23RdUNBt3U&_nc_ht=scontent-sin6-3.xx&oh=03_AdSNfyVmHC1ynKkc06kPhEZvW_v4rCz1fBNMMR1jO5729g&oe=6393E073"
                    >
                </profileCard>
            </div> -->
    </div>
</template>
<style>
</style>
<script>
import profileCard from "../components/Profile.vue"
export default {
    data(){
        return {
            members:[
                {
                    name : "Patinya Saichantadee",
                    nickname : "Tonnow",
                    inGameName :"ColdOriginZ",
                    team : "CNO",
                    year : "KU81",
                    birthday : "11-17-2002",
                    facebook : "https://www.facebook.com/Tpatinya/",
                    github :"https://www.github.com/PatinyaCXLD/",
                    instagram: "https://www.instagram.com/cxld.pty/",
                    detail : "?????????????????????????????? ????????????????????????????????? ??????????????????????????? ??????????????????????????????????????????????????????????????? ???????????????????????????????????????????????????????????????????????????????????????????????????????????????????????? ?????????????????? ?????????????????????????????????????????????????????????????????? ?????????????????????????????????????????????????????????????????????????????????????????? ??????????????? 2 ????????????",
                    image : "https://scontent.fbkk5-4.fna.fbcdn.net/v/t39.30808-6/306148111_1880034558867492_7239761071913403261_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=_XeFqM296J4AX8utin4&_nc_ht=scontent.fbkk5-4.fna&oh=00_AfAeICXwBymDgAushZ-y3tunHsjPAJs5a7MqDMSJpx640g&oe=637655F6"
                },{
                    name : "Sittipong Hemloum",
                    nickname : "Ong",
                    inGameName : "KanaMooKrob",
                    team : "CNO",
                    year : "KU81",
                    birthday : "09-21-2001",
                    facebook : "https://www.facebook.com/profile.php?id=100008313884704",
                    github :"https://www.github.com/ong22280/",
                    instagram: "https://www.instagram.com/sittipongong/",
                    detail : "This is just a test",
                    image : "https://scontent-sin6-2.xx.fbcdn.net/v/t1.15752-9/310835510_684981289522964_3461760171192846605_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=ae9488&_nc_ohc=RbRFs_Ahn1wAX8KvYaR&_nc_ht=scontent-sin6-2.xx&oh=03_AdQtCRMXZcFGk2BujrCs4TT0Z-x4cp8bb_OiUzy9xMIJEA&oe=6393DCA4"
                },{
                    name : "Punnatud Duengkae",
                    nickname : "Nokkok",
                    inGameName : "DraftMaster",
                    team : "CNO",
                    year : "KU81",
                    birthday : "12-27-2002",
                    facebook : "https://www.facebook.com/punnatud.duengkae",
                    github :"https://www.github.com/Punnatud/",
                    instagram: "https://www.instagram.com/nokkokalderaan/",
                    detail : "This is just a test",
                    image : "https://scontent-sin6-3.xx.fbcdn.net/v/t1.15752-9/313894314_664603271857321_204835522882551428_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=ae9488&_nc_ohc=g_nLz-GHp5IAX8DLPcP&tn=9Fdpok23RdUNBt3U&_nc_ht=scontent-sin6-3.xx&oh=03_AdSNfyVmHC1ynKkc06kPhEZvW_v4rCz1fBNMMR1jO5729g&oe=6393E073"
                }
            ],
            name : "Patinya Saichantadee",
            nickname: "Tonnow",
            birthday: "17-11-2002",
            team: "CNO",
            inGameName: "ColdOriginZ",
            year: "KU81",
            image : "https://scontent-sin6-4.xx.fbcdn.net/v/t39.30808-6/306148111_1880034558867492_7239761071913403261_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=X2MKA-ZW1JcAX9v_Uu6&_nc_ht=scontent-sin6-4.xx&oh=00_AfAWqFIQ_bf49w75-KLuajS4IVz1ihVV7PHUk-tzih-vlQ&oe=63706736",
            selected : false,
            detail : "",
        }
    },
    components : {
        profileCard
    },
    methods: {
        getMemberNumber() {
            return 'basis-1/'+this.members.length +" flex justify-center h-fit";
        },
        scrollToElement(refName) {
            var element = this.$refs[refName];
            var top = element.offsetTop;
            
            window.scrollTo(0,top)
        },
        showPopup(name){
            if (name != this.name) {
                this.selected = true;
                this.goToBottom();
            }else if (!this.selected){
                this.selected = true;
                this.goToBottom();
            }else{
                this.goToTop();
                setTimeout( ()=>{
                    this.selected = false;
                    },200
                );
            }
        },
        goToBottom(){
            setTimeout(()=>{
                window.scrollTo({
                    top: document.documentElement.scrollHeight,
                    behavior: 'smooth'
                }),
                10
            })
        },
        goToTop(){
            window.scrollTo({top:0,behavior:'smooth'});
        },
        getHeight(){
            console.log(document.documentElement.scrollHeight)
        }

    },
}
</script>


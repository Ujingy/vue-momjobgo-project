<template>
    <div>
        <v-card
        elevation="2"
        >
            <v-card-title>회원 정보 및 수정</v-card-title>
            <v-card-subtitle>* 는 필수 값입니다.</v-card-subtitle>
            <v-card-text>
                 <v-text-field v-model="user.id" label="* 아이디" disabled></v-text-field>
                 <v-text-field v-model="user.pwd" label="* 현재 비밀번호" type="password"></v-text-field>

                 <v-text-field v-model="user.newPwd" label="새로운 비밀번호" type="password"></v-text-field>
                 <v-text-field v-model="checkPwd" label="새로운 비밀번호 확인" type="password"></v-text-field>
                 <v-text-field v-model="user.name" label="* 이름"></v-text-field>
            </v-card-text>

            <v-card-actions>
                <v-btn @click="modify">수정</v-btn>
                <v-btn @click="deleteUser" color="red" style="color: white;">삭제</v-btn>
            </v-card-actions>
        </v-card>
    </div>
</template>

<script>

export default {

    data() {
        return {
            user : {
                id : '',
                name : '',
                pwd : '',
                newPwd : ''
            },

            checkPwd : ''
        }
    },

    created() {
        this.refreshUser();
    },

    methods: {

        async refreshUser(){
            // 유저 정보를 호출하고 vuex의 유저정보를 같이 갱신해 준다.
        },

        async modify(){

            // 새로운 비밀번호가 입력되었을 경우 
            if(this.checkPwd !== this.user.newPwd){
                alert("비밀번호 확인이 일치하지 않습니다.");
                return false;
            }

            // 유저 정보를 수정. ( 새로운 비밀번호를 입력할때 newPwd에 값을 넣으면 됨. 비밀번호를 변경하지 않을때에는 newPwd에 null 값을 넣으면 됨.)

        },

        async deleteUser(){

            // 유저 정보를 삭제.

        }
    },




}
</script>
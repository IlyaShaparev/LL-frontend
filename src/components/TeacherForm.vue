<template>
    <div class="taskform__wrapper">
        <!-- Navbar для формы -->
        <div class="nav__wrapper">
            <ul class="nav__list">
                <li @click="switchTabs(0)" class="nav__list-item active">Задача</li>
                <li @click="switchTabs(1)" class="nav__list-item">Данные</li>
                <li @click="switchTabs(2)" class="nav__list-item">Группы</li>
            </ul>
        </div>
        <form action="" method="post" class="form__wrapper">
            <!-- Title и Condition -->
            <div class="general__block" v-if="g_tab == 0">
                <label class="title__description">
                    <span>Придумайте название задаче</span>
                    <input v-model="task_name" type="text" class="title" placeholder="Изучаем ..." required>
                </label>
                <label class="condition__description">
                    <span>Опишите суть задачи</span>
                    <textarea v-model="task_condition" class="condition" placeholder="Напишите функцию ..." required></textarea>
                </label>
            </div>
            <!-- Tests and GoalSolution -->
            <div class="data__block" v-else-if="g_tab == 1">
                <label for="test" class="desc test-data__description">
                    <span>Прикрепите тесты!</span>
                    <div class="btn">Выбрать</div>
                    <input type="file" name="data_test" id="test" class="test-data" required>
                </label>
                <label for="solution" class="desc goal-solution__description">
                    <span>Покажите ребятам своё эталонное решение!</span>
                    <div class="btn">Выбрать</div>
                    <input type="file" name="goal_solution" id="solution" class="goal-solution" required>
                </label>
            </div>
            <!-- Groups -->
            <div class="groups__block" v-else>
                <div class="group__item">
                    <label for="group-1" class="group__btn">
                        <input type="checkbox" name="group" class="old-btn" id="group-1">
                        <span class="new-btn">9 "А"</span>
                    </label>
                </div>
                <div class="group__item">
                    <label for="group-2" class="group__btn">
                        <input type="checkbox" name="group" class="old-btn" id="group-2">
                        <span class="new-btn">10 "Б"</span>
                    </label>
                </div>
                <div class="group__item">
                    <label for="group-3" class="group__btn">
                        <input type="checkbox" name="group" class="old-btn" id="group-3">
                        <span class="new-btn">9 "Г"</span>
                    </label>
                </div>
                <div class="group__item">
                    <label for="group-4" class="group__btn">
                        <input type="checkbox" name="group" class="old-btn" id="group-4">
                        <span class="new-btn">9 "В"</span>
                    </label>
                </div>
            </div>
            <input type="submit" value="Выложить" class="submit-btn">
        </form>
    </div>
</template>
<script>
    let g_tab = 0;
    let task_name = '';
    let task_condition = '';

    export default {
        data() {
            return {
                g_tab, task_name, task_condition
            }
        },
        methods: {
            switchTabs(n) {
                let tabs = document.querySelectorAll(".nav__list-item")
                tabs.forEach((tab) => tab.classList.remove("active"));
                tabs[n].classList.add("active");
                this.g_tab = n;
            },
            onTitle(e) {
                this.task_name = e.target.task_name;
            },
            onCondition(e) {
                this.task_condition = e.target.task_condition;
            }
        },
        name: "TeacherForm"
    }
</script>
<style scoped>
    .taskform__wrapper {
        flex: 1 0 auto;
        width: 80%;
        margin: 50px auto;
        border-radius: 20px;
        background: rgb(248,249,250);
    }

    .nav__wrapper {
        width: 100%;
    }

    .nav__list {
        width: 100%;
        list-style: none;
        display: flex;
        justify-content: center;
        align-items: center;
        border-top-left-radius: 15px;
        border-top-right-radius: 15px;
        overflow: hidden;
    }

    .nav__list-item {
        width: 35%;
        padding: 10px;
        text-align: center;
        font-family: 'Open Sans';
        font-weight: 400;
        font-size: 25px;
    }

    .nav__list-item:hover {
        background: #81A4CD;
        cursor: pointer;
    }

    .active {
        background: #81A4CD;
    }

    .form__wrapper {
        background: #81A4CD;
        font-size: 20px;
        font-weight: 400;
        font-family: 'Open Sans';
        padding: 50px;
    }

    .general__block {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        gap: 50px;
    }

    .title__description {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
        position: relative;
    }

    .title__description span {
        position: absolute;
        top: -15px;
        left: 20px;
        background: #81A4CD;
        padding: 0 10px;
        text-transform: uppercase;
        font-weight: 300;
    }

    .title {
        outline: 0;
        border-radius: 5px;
        width: 50%;
        padding: 10px 20px;
        line-height: 36px;
        font-size: 18px;
        background: #81A4CD;
        border: 1px  solid black;
        font-family: 'Open Sans';
        font-weight: 300;
        letter-spacing: 2px;
    }

    .title::placeholder {
        font-size: 18px;
        font-family: 'Open Sans';
    }

    .title:focus  {
        box-shadow: 1px 1px 3px black;
    }

    .title::selection {
        background: aliceblue;
    }

    .condition__description {
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        position: relative;
    }

    .condition__description span {
        align-self: flex-start;
        position: absolute;
        top: -15px;
        left: 20px;
        background: #81A4CD;
        padding: 0 10px;
        text-transform: uppercase;
        font-weight: 300;
    }

    .condition {
        outline: 0;
        resize: none;
        border-radius: 5px;
        width: 100%;
        padding: 20px 20px;
        line-height: 36px;
        font-size: 18px;
        background: #81A4CD;
        border: 1px  solid black;
        font-family: 'Open Sans';
        font-weight: 300;
        letter-spacing: 2px;
        height: 300px;
    }

    .condition:focus  {
        box-shadow: 1px 1px 3px black;
    }

    .condition::selection {
        background: aliceblue;
    }

    .condition::placeholder {
        font-size: 18px;
        font-family: 'Open Sans';
    }

    .groups__block {
        display: flex;
        flex-wrap: wrap;
        gap: 30px;
    }

    .group__item {
        width: calc(50% - 30px);
    }

    .group__btn {
        display: block;
        width: 50%;
        margin: 0 auto;
    }

    .new-btn {
        display: block;
        width: 100%;
        background: #19c5a0;
        border-radius: 20px;
        text-align: center;
        padding: 10px 20px;
        border: 1px solid #00ffc8;
        cursor: pointer;
        transition: all 0.5s;
    }

    .new-btn:hover {
        background-color: #00ffc8;
        transform: scale(1.1);
    }

    .old-btn {
        display: none;
    }

    .old-btn:checked + .new-btn {
        transform: scale(1.1);
        background-color: #00ffc8;
    }

    .data__block {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 40px;
    }

    .desc {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 20px;
        cursor: pointer;
    }

    label.desc .btn {
        display: block;
        width: 30%;
        background: #19c5a0;
        border-radius: 20px;
        text-align: center;
        padding: 10px 20px;
        border: 1px solid #00ffc8;
        transition: all 0.5s;
    }

    label.desc .btn:hover {
        background: #00ffc8;
        transform: scale(1.1);
    }

    .test-data {
        display: none;
    }

    .goal-solution {
        display: none;
    }

    .submit-btn {
        display: block;
        width: 30%;
        background: #473BF0;
        border-radius: 20px;
        text-align: center;
        padding: 10px 20px;
        border: 1px solid #6e65ee;
        cursor: pointer;
        transition: all 0.5s;
        font-size: 20px;
        font-weight: 600;
        margin: 0px auto;
        margin-top: 50px;
    }

    .submit-btn:hover {
        background-color: #6e65ee;
        transform: scale(1.1);
    }
</style>
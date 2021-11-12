<template>
  <div class="home">
    <header>
      <h1>爬虫机器人展示平台</h1>
      <div class="showTime">当前时间：2021年9月<span></span></div>
    </header>
    <section class="mainbox">
      <!-- 左侧  -->
      <div class="column">
        <leftOne></leftOne>
        <el-row :gutter="20">
          <el-col :span="12">
            <leftTwo></leftTwo>
          </el-col>
          <el-col :span="12">
            <leftThree></leftThree>
          </el-col>
        </el-row>
        <leftFour></leftFour>
        >
      </div>

      <!-- 中间  -->
      <div class="column">
        <!-- <dataBasic :dataStatistic="updateStatistic"></dataBasic> -->
        <el-row :gutter="20">
          <el-col
            :span="8"
            :offset="1"
          >
            <centerOne :data='data'></centerOne>
          </el-col>
          <el-col
            :span="8"
            :offset="7"
          >
            <centerTwo></centerTwo>
          </el-col>
        </el-row>
        <div class="map">
          <china1></china1>
          <div class="map1"></div>
          <div class="map2"></div>
          <div class="map3"></div>
        </div>
      </div>

      <!-- 右边  -->
      <div class="column">
        <rightOne></rightOne>
        <div>
          <el-row :gutter="20">
            <el-col :span="12">
              <peope-num></peope-num>
            </el-col>
            <el-col :span="12">
              <people-sex></people-sex>
            </el-col>
          </el-row>
        </div>
        <pie1></pie1>
        <bar></bar>
      </div>
    </section>
  </div>
</template>

<script>
import bar from "@/components/echarts/bar";
import leftOne from "@/components/echarts/leftone";
import eline from "@/components/echarts/line";
import line1 from "@/components/echarts/line1";
import pie from "@/components/echarts/pie";
import pie1 from "@/components/echarts/pie1";
import china1 from "@/components/echarts/china";
import dataBasic from "@/components/robotData/data_basic";
import dataRobotOn from "@/components/robotData/data_robotOn";
import dataOn from "@/components/robotData/data_on";
import dataInfo from "@/components/robotData/data_info";
import leftFour from "@/components/robotData/leftfour";
import peopleNum from "@/components/echarts/people-num";
import peopleSex from "@/components/echarts/people-sex";
import PeopeNum from "@/components/echarts/people-num";
import PeopleSex from "@/components/echarts/people-sex";
import leftTwo from "@/components/echarts/lefttwo";
import leftThree from "@/components/echarts/leftthree";
import centerOne from "@/components/echarts/centerone";
import centerTwo from "@/components/echarts/centertwo";
import rightOne from "@/components/robotData/rightone";
export default {
  name: "",
  data() {
    return {
      updateStatistic: [],
      data: {},
    };
  },
  components: {
    bar,
    leftOne,
    pie1,
    pie,
    eline,
    line1,
    china1,
    dataBasic,
    dataRobotOn,
    dataOn,
    dataInfo,
    peopleNum,
    peopleSex,
    PeopeNum,
    PeopleSex,
    leftTwo,
    leftThree,
    leftFour,
    centerOne,
    centerTwo,
    rightOne,
  },
  methoRightoneds: {
    // 更新dataBasic图
    updateDataBasic() {
      this.updateStatistic = [
        {
          name: "平台数量",
          value: "7",
        },
        {
          name: "机器人数量",
          value: "450",
        },
        {
          name: "爬虫数量",
          value: "560",
        },
        {
          name: "分布位置数量",
          value: "45",
        },
        {
          name: "新闻总量",
          value: "125633",
        },
        {
          name: "用户数量",
          value: "7215",
        },
      ];
    },
  },
  mounted() {
    this.updateDataBasic();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
.home {
  min-height: 100vh;
  background-color: #06164a;
  header {
    position: relative;
    height: 1.25rem;
    background: url(../static/images/head_bg.png) no-repeat top center;
    background-size: 100% 100%;
    h1 {
      font-size: 0.475rem;
      color: #fff;
      text-align: center;
      line-height: 1rem;
    }
    .showTime {
      position: absolute;
      top: 0;
      right: 0.375rem;
      line-height: 0.9375rem;
      font-size: 0.25rem;
      color: rgba(255, 255, 255, 0.7);
    }
  }
  .mainbox {
    // min-height: 1024px;
    // max-width: 1920px;
    padding: 0.125rem 0.125rem 0;
    display: flex;
    .column {
      flex: 2;
      overflow: hidden;
      &:nth-child(2) {
        flex: 4;
        overflow: hidden;
      }
    }
  }
  .panel-right {
    position: relative;
    border: 1px solid rgba(25, 186, 139, 0.17);
    background: rgba(255, 255, 255, 0.04) url(../static/images/line\(1\).png);
    margin-bottom: 0.1875rem;
    &::before {
      position: absolute;
      top: 0;
      left: 0;
      content: "";
      width: 10px;
      height: 10px;
      border-top: 2px solid #02a6b5;
      border-left: 2px solid #02a6b5;
      border-radius: 20%;
    }
    &::after {
      position: absolute;
      top: 0;
      right: 0;
      content: "";
      width: 10px;
      height: 10px;
      border-top: 2px solid #02a6b5;
      border-right: 2px solid #02a6b5;
      border-radius: 20%;
    }
    .panel-footer {
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      &::before {
        position: absolute;
        bottom: 0;
        left: 0;
        content: "";
        width: 10px;
        height: 10px;
        border-bottom: 2px solid #02a6b5;
        border-left: 2px solid #02a6b5;
        border-radius: 20%;
      }
      &::after {
        position: absolute;
        bottom: 0;
        right: 0;
        content: "";
        width: 10px;
        height: 10px;
        border-bottom: 2px solid #02a6b5;
        border-right: 2px solid #02a6b5;
        border-radius: 20%;
      }
    }

    h2 {
      height: 0.5rem;
      line-height: 0.5rem;
      text-align: center;
      color: #fff;
      font-size: 0.25rem;
      font-weight: 400;
      a {
        color: #fff;
        text-decoration: underline;
      }
    }
    .chart {
      height: 3rem;
    }
  }
  .panel {
    position: relative;
    height: 1.5 1.875rem;
    border: 1px solid rgba(25, 186, 139, 0.17);
    background: rgba(255, 255, 255, 0.04) url(../static/images/line\(1\).png);
    margin-bottom: 0.1875rem;
    &::before {
      position: absolute;
      top: 0;
      left: 0;
      content: "";
      width: 10px;
      height: 10px;
      border-top: 2px solid #02a6b5;
      border-left: 2px solid #02a6b5;
      border-radius: 20%;
    }
    &::after {
      position: absolute;
      top: 0;
      right: 0;
      content: "";
      width: 10px;
      height: 10px;
      border-top: 2px solid #02a6b5;
      border-right: 2px solid #02a6b5;
      border-radius: 20%;
    }
    .panel-footer {
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      &::before {
        position: absolute;
        bottom: 0;
        left: 0;
        content: "";
        width: 10px;
        height: 10px;
        border-bottom: 2px solid #02a6b5;
        border-left: 2px solid #02a6b5;
        border-radius: 20%;
      }
      &::after {
        position: absolute;
        bottom: 0;
        right: 0;
        content: "";
        width: 10px;
        height: 10px;
        border-bottom: 2px solid #02a6b5;
        border-right: 2px solid #02a6b5;
        border-radius: 20%;
      }
    }

    h2 {
      height: 0.5rem;
      line-height: 0.5rem;
      text-align: center;
      color: #fff;
      font-size: 0.25rem;
      font-weight: 400;
      a {
        margin: 0 0.05rem;
        color: #fff;
        text-decoration: underline;
      }
    }
    .chart {
      height: 3rem;
    }
  }
  .no {
    background: rgba(101, 132, 226, 0.1);
    padding: 0.1875rem;
    .no-hd {
      position: relative;
      border: 1px solid rgba(25, 186, 139, 0.17);
      &::before {
        content: "";
        position: absolute;
        width: 30px;
        height: 10px;
        border-top: 2px solid #02a6b5;
        border-left: 2px solid #02a6b5;
        top: 0;
        left: 0;
      }
      &::after {
        content: "";
        position: absolute;
        width: 30px;
        height: 10px;
        border-bottom: 2px solid #02a6b5;
        border-right: 2px solid #02a6b5;
        right: 0;
        bottom: 0;
      }
      ul {
        display: flex;
        li {
          position: relative;
          flex: 1;
          text-align: center;
          height: 1rem;
          line-height: 1rem;
          font-size: 0.875rem;
          color: #ffeb7b;
          padding: 0.05rem 0;
          font-family: electronicFont;
          font-weight: bold;
          &:first-child::after {
            content: "";
            position: absolute;
            height: 50%;
            width: 1px;
            background: rgba(255, 255, 255, 0.2);
            right: 0;
            top: 25%;
          }
        }
      }
    }
    .no-bd ul {
      display: flex;
      li {
        flex: 1;
        height: 0.5rem;
        line-height: 0.5rem;
        text-align: center;
        font-size: 0.225rem;
        color: rgba(255, 255, 255, 0.7);
        padding-top: 0.125rem;
      }
    }
  }
  .map {
    position: relative;
    height: 10.125rem;
    .chart {
      position: absolute;
      top: 0;
      left: 0;
      z-index: 5;
      height: 10.125rem;
      width: 100%;
    }
    .map1,
    .map2,
    .map3 {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 6.475rem;
      height: 6.475rem;
      background: url(../static/images/map.png) no-repeat;
      background-size: 100% 100%;
      opacity: 0.3;
    }
    .map2 {
      width: 8.0375rem;
      height: 8.0375rem;
      background-image: url(../static/images/lbx.png);
      opacity: 0.6;
      animation: rotate 15s linear infinite;
      z-index: 2;
    }
    .map3 {
      width: 7.075rem;
      height: 7.075rem;
      background-image: url(../static/images/jt.png);
      animation: rotate1 10s linear infinite;
    }

    @keyframes rotate {
      from {
        transform: translate(-50%, -50%) rotate(0deg);
      }
      to {
        transform: translate(-50%, -50%) rotate(360deg);
      }
    }
    @keyframes rotate1 {
      from {
        transform: translate(-50%, -50%) rotate(0deg);
      }
      to {
        transform: translate(-50%, -50%) rotate(-360deg);
      }
    }
  }

  @media screen and (max-width: 1024px) {
    html {
      font-size: 42px !important;
    }
  }
  @media screen and (min-width: 1920) {
    html {
      font-size: 80px !important;
    }
  }
  .el-table__body-wrapper::-webkit-scrollbar {
    width: 6px;
    height: 6px; /**/
  }
  .el-table__body-wrapper::-webkit-scrollbar-track {
    background: rgb(239, 239, 239);
    border-radius: 2px;
  }
  .el-table__body-wrapper::-webkit-scrollbar-thumb {
    background: #2f90b5;
    border-radius: 10px;
  }
  .el-table__body-wrapper::-webkit-scrollbar-thumb:hover {
    background: #2f90b5;
  }
  .el-table {
    font-size: 0.2rem;
  }
  .el-table::before {
    height: 0;
  }
  .el-table td.el-table__cell,
  .el-table th.el-table__cell.is-leaf {
    border-bottom: none;
  }
  .el-table th.el-table__cell,
  .el-table tr,
  .el-table,
  .el-table__expanded-cell {
    background: none;
  }
  .el-table .el-table__cell {
    padding: 8px 0;
  }
  .el-table--enable-row-transition .el-table__body td.el-table__cell {
    color: #2f90b5;
  }
  .el-table--enable-row-hover .el-table__body tr:hover > td.el-table__cell {
    background-color: #091123;
  }
}
</style>

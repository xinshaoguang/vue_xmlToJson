<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
// import x2j from "./xmlToJson";
import x2j from "xml-js";
export default {
  name: "Home",
  // components: {
  //   HelloWorld
  // }
  data() {
    return {
      xmlStr: `<?xml version="1.0" encoding="UTF-8"?>
    <bpmn:definitions
      xmlns:bpmn="http://www.omg.org/spec/BPMN/20100524/MODEL"
      xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI"
      xmlns:dc="http://www.omg.org/spec/DD/20100524/DC"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xmlns:ext="http://www.fa.com/schema/1.0/EXT"
      xmlns:di="http://www.omg.org/spec/DD/20100524/DI"
      xmlns:activiti="http://activiti.org/bpmn"
      id="Definitions_17m7czq13f"
      targetNamespace="http://bpmn.io/schema/bpmn"
    >
      <ext:TaskEvent
        id="mailEvent_5890615"
        event="mailEvent"
        callTime="TASK_CREATED"
        scope="0"
        callNodes="Activity_0lkz2el"
        isAsync="1"
      >
        <ext:EventProperty
          id="EventProperty_0xnokx8"
          key="mailTemplate"
          value="PreCloseNodeMail.ftl"
        />
        <ext:EventProperty
          id="EventProperty_10gntyi"
          key="notifyPersons"
          value="905010938@qq.com"
        />
        <ext:EventProperty
          id="EventProperty_0ub4tes"
          key="notifyReqDirectMgr"
          value="1"
        />
        <ext:EventProperty
          id="EventProperty_1vdjlvq"
          key="copyPersons"
          value="905010938@qq.com"
        />
        <ext:EventProperty
          id="EventProperty_1w3st6p"
          key="copyReqDirectMgr"
          value="1"
        />
      </ext:TaskEvent>
      <ext:FormDefinition
        id="FormDefinition_0ub5yea"
        formKey="testFormKey:1"
        type="inner"
        startForm="1"
        editorActivityDefIds=""
        visibleActivityDefIds=""
      >
      </ext:FormDefinition>
      <ext:FormDefinition
        id="FormDefinition_0uf8yea"
        formKey="testFormTwo:1"
        type="inner"
        startForm="q"
        editorActivityDefIds="Activity_15qtm8l"
        visibleActivityDefIds="Activity_15qtm8l,Activity_10ij56c"
      >
        <outForm id='123' name='xiaoming'></outForm>
      </ext:FormDefinition>
      <ext:FormDefinition
        id="FormDefinition_0rn5yea"
        formKey="testFormThirdKey:1"
        type="inner"
        startForm="q"
        editorActivityDefIds="Activity_1xescee,Activity_1ddekk5"
        visibleActivityDefIds="Activity_1ddekk5,Activity_1xescee"
      >
      </ext:FormDefinition>
      <bpmn:process
        id="FormExtTestProcess1"
        name="事件表单测试流程"
        isExecutable="true"
      >
        <bpmn:startEvent
          id="StartEvent_1"
          name="开始"
          activiti:initiator="startUser"
        >
          <bpmn:outgoing>Flow_0o7yrzq</bpmn:outgoing>
        </bpmn:startEvent>
        <bpmn:userTask id="Activity_0lkz2el" name="用户任务1">
          <bpmn:incoming>Flow_0o7yrzq</bpmn:incoming>
          <bpmn:outgoing>Flow_0fdpu6k</bpmn:outgoing>
        </bpmn:userTask>
        <bpmn:userTask id="Activity_15qtm8l" name="用户任务2">
          <bpmn:incoming>Flow_0fdpu6k</bpmn:incoming>
          <bpmn:outgoing>Flow_0mcl36l</bpmn:outgoing>
        </bpmn:userTask>
        <bpmn:userTask id="Activity_10ij56c" name="用户任务3">
          <bpmn:incoming>Flow_0mcl36l</bpmn:incoming>
          <bpmn:outgoing>Flow_09d8qub</bpmn:outgoing>
        </bpmn:userTask>
        <bpmn:userTask id="Activity_1xescee" name="用户任务5">
          <bpmn:incoming>Flow_0dz59ri</bpmn:incoming>
          <bpmn:outgoing>Flow_0iamnn8</bpmn:outgoing>
        </bpmn:userTask>
        <bpmn:userTask id="Activity_1ddekk5" name="用户任务4">
          <bpmn:incoming>Flow_09d8qub</bpmn:incoming>
          <bpmn:outgoing>Flow_0dz59ri</bpmn:outgoing>
        </bpmn:userTask>
        <bpmn:endEvent id="Event_0kputyw" name="结束节点">
          <bpmn:incoming>Flow_0iamnn8</bpmn:incoming>
        </bpmn:endEvent>
        <bpmn:sequenceFlow
          id="Flow_0o7yrzq"
          sourceRef="StartEvent_1"
          targetRef="Activity_0lkz2el"
        />
        <bpmn:sequenceFlow
          id="Flow_0fdpu6k"
          sourceRef="Activity_0lkz2el"
          targetRef="Activity_15qtm8l"
        />
        <bpmn:sequenceFlow
          id="Flow_0mcl36l"
          sourceRef="Activity_15qtm8l"
          targetRef="Activity_10ij56c"
        />
        <bpmn:sequenceFlow
          id="Flow_09d8qub"
          sourceRef="Activity_10ij56c"
          targetRef="Activity_1ddekk5"
        />
        <bpmn:sequenceFlow
          id="Flow_0dz59ri"
          sourceRef="Activity_1ddekk5"
          targetRef="Activity_1xescee"
        />
        <bpmn:sequenceFlow
          id="Flow_0iamnn8"
          sourceRef="Activity_1xescee"
          targetRef="Event_0kputyw"
        />
      </bpmn:process>
      <bpmndi:BPMNDiagram id="BPMNDiagram_1">
        <bpmndi:BPMNPlane id="BPMNPlane_1" bpmnElement="testProcess">
          <bpmndi:BPMNEdge id="Flow_0o7yrzq_di" bpmnElement="Flow_0o7yrzq">
            <di:waypoint x="150" y="179" />
            <di:waypoint x="195" y="179" />
            <di:waypoint x="195" y="180" />
            <di:waypoint x="240" y="180" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNEdge id="Flow_0fdpu6k_di" bpmnElement="Flow_0fdpu6k">
            <di:waypoint x="280" y="179" />
            <di:waypoint x="325" y="179" />
            <di:waypoint x="325" y="180" />
            <di:waypoint x="370" y="180" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNEdge id="Flow_0mcl36l_di" bpmnElement="Flow_0mcl36l">
            <di:waypoint x="410" y="179" />
            <di:waypoint x="450" y="179" />
            <di:waypoint x="450" y="190" />
            <di:waypoint x="490" y="190" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNEdge id="Flow_09d8qub_di" bpmnElement="Flow_09d8qub">
            <di:waypoint x="530" y="179" />
            <di:waypoint x="575" y="179" />
            <di:waypoint x="575" y="180" />
            <di:waypoint x="620" y="180" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNEdge id="Flow_0dz59ri_di" bpmnElement="Flow_0dz59ri">
            <di:waypoint x="660" y="179" />
            <di:waypoint x="710" y="179" />
            <di:waypoint x="710" y="180" />
            <di:waypoint x="760" y="180" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNEdge id="Flow_0iamnn8_di" bpmnElement="Flow_0iamnn8">
            <di:waypoint x="800" y="179" />
            <di:waypoint x="930" y="179" />
          </bpmndi:BPMNEdge>
          <bpmndi:BPMNShape
            id="_BPMNShape_StartEvent_2"
            bpmnElement="StartEvent_1"
          >
            <dc:Bounds x="110" y="159" width="40" height="40" />
            <bpmndi:BPMNLabel>
              <dc:Bounds x="59" y="172" width="23" height="14" />
            </bpmndi:BPMNLabel>
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape
            id="Activity_0lkz2el_di"
            bpmnElement="Activity_0lkz2el"
          >
            <dc:Bounds x="240" y="159" width="40" height="40" />
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape
            id="Activity_15qtm8l_di"
            bpmnElement="Activity_15qtm8l"
          >
            <dc:Bounds x="370" y="159" width="40" height="40" />
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape
            id="Activity_10ij56c_di"
            bpmnElement="Activity_10ij56c"
          >
            <dc:Bounds x="490" y="159" width="40" height="40" />
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape
            id="Activity_1ddekk5_di"
            bpmnElement="Activity_1ddekk5"
          >
            <dc:Bounds x="620" y="159" width="40" height="40" />
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape id="Event_0kputyw_di" bpmnElement="Event_0kputyw">
            <dc:Bounds x="930" y="159" width="40" height="40" />
            <bpmndi:BPMNLabel>
              <dc:Bounds x="928" y="202" width="44" height="14" />
            </bpmndi:BPMNLabel>
          </bpmndi:BPMNShape>
          <bpmndi:BPMNShape
            id="Activity_1xescee_di"
            bpmnElement="Activity_1xescee"
          >
            <dc:Bounds x="760" y="159" width="40" height="40" />
          </bpmndi:BPMNShape>
        </bpmndi:BPMNPlane>
      </bpmndi:BPMNDiagram> </bpmn:definitions
    >`,
    xmlStr1:`<?xml version="1.0" encoding="UTF-8"?>
<bpmn:definitions xmlns:bpmn="http://www.omg.org/spec/BPMN/20100524/MODEL" xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI" xmlns:dc="http://www.omg.org/spec/DD/20100524/DC" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ext="http://www.fa.com/schema/1.0/EXT" xmlns:di="http://www.omg.org/spec/DD/20100524/DI" xmlns:activiti="http://activiti.org/bpmn" xmlns:extA1="http://www.a1bpm.com/schema/1.0/A1" id="Definitions_17m7czq" targetNamespace="http://bpmn.io/schema/bpmn">
 <ext:TaskEvent id="processInfoPushEvent_5283110" event="processInfoPushEvent" callTime="TASK_CREATED" scope="1" callNodes="Activity_1an2dov,Activity_0c4l8yu,Activity_0x3w80w" isAsync="1" />
  <ext:FormDefinition id="FormDefinition_5133135" type="out" startForm="0" visibleActivityDefIds="Activity_1an2dov,Activity_0c4l8yu,Activity_0x3w80w" editorActivityDefIds="Activity_0c4l8yu">
    <ext:OutForm id="OutForm_7459141" systemName="系统名称" url="url" param="请求参数" requestMethod="post" />
  </ext:FormDefinition>
  <ext:FormDefinition id="FormDefinition_1154344" formKey="CheckList:2" type="inner" startForm="1" visibleActivityDefIds="Activity_1an2dov" editorActivityDefIds="Activity_1an2dov,Activity_0c4l8yu" />
  <ext:UserRule id="UserRule_4506400" nodeId="Activity_0c4l8yu" pluginType="depHead" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="" specId="" />
  <ext:UserRule id="UserRule_6458822" nodeId="Activity_0c4l8yu" pluginType="users" pluginVal="" logicCal="or" ruleId="spec" ruleDisplayName="[指定用户]孙磊" specId="sunlei" />
  <ext:UserRule id="UserRule_7359253" nodeId="Activity_0c4l8yu" pluginType="users" pluginVal="" logicCal="or" ruleId="start" ruleDisplayName="发起人" specId="" />
  <ext:UserRule id="UserRule_9092295" nodeId="Activity_0c4l8yu" pluginType="org" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="[部门]研发子部门1" specId="fa_dept1_1" />
  <ext:UserRule id="UserRule_7188575" nodeId="Activity_0x3w80w" pluginType="depHead" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="" specId="" />
  <ext:UserRule id="UserRule_9891167" nodeId="Activity_0x3w80w" pluginType="org" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="[部门]销售部" specId="fa_dept2" />
  <ext:UserRule id="UserRule_6785549" nodeId="Activity_0x3w80w" pluginType="users" pluginVal="" logicCal="or" ruleId="spec" ruleDisplayName="[指定用户]吴明迪" specId="wumingdi" />
  <ext:UserRule id="UserRule_1890240" nodeId="Activity_0x3w80w" pluginType="users" pluginVal="" logicCal="or" ruleId="start" ruleDisplayName="发起人" specId="" />
  <ext:UserRule id="UserRule_4698951" nodeId="Activity_1an2dov" pluginType="depHead" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="" specId="" />
  <ext:UserRule id="UserRule_1125407" nodeId="Activity_1an2dov" pluginType="org" pluginVal="" logicCal="or" ruleId="" ruleDisplayName="[部门]研发部" specId="fa_dept1" />
  <ext:UserRule id="UserRule_4104423" nodeId="Activity_1an2dov" pluginType="users" pluginVal="" logicCal="or" ruleId="spec" ruleDisplayName="[指定用户]陈和磊,张三" specId="chenhelei,zhangsan" />
  <ext:UserRule id="UserRule_7275084" nodeId="Activity_1an2dov" pluginType="users" pluginVal="" logicCal="or" ruleId="start" ruleDisplayName="发起人" specId="" />
  <bpmn:process id="Process_02okg1u" name="请假流程" isExecutable="true">
    <bpmn:startEvent id="StartEvent_1" name="开始" activiti:initiator="startUser">
      <bpmn:outgoing>Flow_0icvx6n</bpmn:outgoing>
    </bpmn:startEvent>
    <bpmn:userTask id="Activity_1an2dov" name="用户任务">
      <bpmn:incoming>Flow_0icvx6n</bpmn:incoming>
      <bpmn:outgoing>Flow_0k6knf0</bpmn:outgoing>
    </bpmn:userTask>
    <bpmn:serviceTask id="Activity_0c4l8yu" name="服务任务">
      <bpmn:incoming>Flow_0xwt14c</bpmn:incoming>
      <bpmn:outgoing>Flow_1r8kmdg</bpmn:outgoing>
    </bpmn:serviceTask>
    <bpmn:endEvent id="Event_1f13ue6" name="结束节点">
      <bpmn:incoming>Flow_1r8kmdg</bpmn:incoming>
    </bpmn:endEvent>
    <bpmn:userTask id="Activity_0x3w80w" name="用户任务">
      <bpmn:incoming>Flow_0k6knf0</bpmn:incoming>
      <bpmn:outgoing>Flow_0xwt14c</bpmn:outgoing>
    </bpmn:userTask>
    <bpmn:sequenceFlow id="Flow_0icvx6n" sourceRef="StartEvent_1" targetRef="Activity_1an2dov" />
    <bpmn:sequenceFlow id="Flow_0k6knf0" sourceRef="Activity_1an2dov" targetRef="Activity_0x3w80w" />
    <bpmn:sequenceFlow id="Flow_0xwt14c" sourceRef="Activity_0x3w80w" targetRef="Activity_0c4l8yu" />
    <bpmn:sequenceFlow id="Flow_1r8kmdg" sourceRef="Activity_0c4l8yu" targetRef="Event_1f13ue6" />
  </bpmn:process>
  <bpmndi:BPMNDiagram id="BPMNDiagram_1">
    <bpmndi:BPMNPlane id="BPMNPlane_1" bpmnElement="Process_02okg1u">
      <bpmndi:BPMNEdge id="Flow_0icvx6n_di" bpmnElement="Flow_0icvx6n">
        <di:waypoint x="168" y="110" />
        <di:waypoint x="270" y="110" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0k6knf0_di" bpmnElement="Flow_0k6knf0">
        <di:waypoint x="320" y="150" />
        <di:waypoint x="320" y="200" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0xwt14c_di" bpmnElement="Flow_0xwt14c">
        <di:waypoint x="370" y="240" />
        <di:waypoint x="410" y="240" />
        <di:waypoint x="410" y="180" />
        <di:waypoint x="450" y="180" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1r8kmdg_di" bpmnElement="Flow_1r8kmdg">
        <di:waypoint x="550" y="150" />
        <di:waypoint x="596" y="150" />
        <di:waypoint x="596" y="140" />
        <di:waypoint x="642" y="140" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNShape id="Activity_1an2dov_di" bpmnElement="Activity_1an2dov">
        <dc:Bounds x="270" y="70" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0c4l8yu_di" bpmnElement="Activity_0c4l8yu">
        <dc:Bounds x="450" y="110" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_1f13ue6_di" bpmnElement="Event_1f13ue6">
        <dc:Bounds x="642" y="122" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="638" y="161" width="43" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0x3w80w_di" bpmnElement="Activity_0x3w80w">
        <dc:Bounds x="270" y="200" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="_BPMNShape_StartEvent_2" bpmnElement="StartEvent_1">
        <dc:Bounds x="132" y="92" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="139" y="128" width="22" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
    </bpmndi:BPMNPlane>
  </bpmndi:BPMNDiagram>
</bpmn:definitions>`
    };
    
  },
  mounted() {
    var myOptions = {
      // mergeCDATA: false,
      // xmlns: false,
      // attrsAsObject: false
    };

    // var json = x2j.parseString(this.xmlStr1);
    var json = x2j.xml2js(this.xmlStr1,{compact: true, spaces: 4,alwaysArray:true});
    console.log(json, "json");
    // var json1=x2j.js2xml(json,{compact: true, ignoreComment: true, spaces: 4})
    // console.log(json1)
  },
};
</script>

if(app.documents.length==0){
    alert('Vui lòng mở master')
}
else{
var doc=app.activeDocument;
var myDocumentName = doc.name;
var thePath = doc.filePath;
var array=[];
var array1=[]
var file = new File("/Volumes/spring-work/JYSK/7_EasyCatalog/Rename Files Instore.text")
file.open("r")
var cpName = file.readln()
file.close();
app.doScript('/Users/chau.huynh/Library/Preferences/Adobe InDesign/Version 16.0/en_US/Scripts/Scripts Panel/Library/Library_function.jsx')
getcountrycode()
//var country=[['1023','DE'],['1024','AT'],['1025','CH'],['1026','FR'],['1026','ES'],['1028','IT'],['1029','PT'],['2025','CH-IT'],['2027','ES-CAT'],['2028','IT-DE'],['3025','CH-FR']]
var myWindow =  new Window('dialog','Create A1,A0');
    //myWindow.orientation='row'
    myWindow.alignChildren='top'
var panelgroup = myWindow.add('group')
    panelgroup.orientation='column'
    panelgroup.alignChildren='center'   
    var panel = panelgroup.add('group')
        panel.orientation='row'
        panel.alignChildren='top'  
        var panel1 =  panel.add('panel')
        for(var i=0;i<array.length/6;i++){
            panel1.add('checkbox',undefined,array[i][1])        
        }
        var panel2 =  panel.add('panel')
        for(var i=Math.round(array.length/6);i<Math.round(array.length/6)*2;i++){            
            panel2.add('checkbox',undefined,array[i][1])
        }
        var panel3 =  panel.add('panel')
        for(var i=Math.round(array.length/6)*2;i<Math.round(array.length/6)*3;i++){
            panel3.add('checkbox',undefined,array[i][1])
        }
        var panel4 =  panel.add('panel')
        for(var i=Math.round(array.length/6)*3;i<Math.round(array.length/6)*4;i++){
            panel4.add('checkbox',undefined,array[i][1])
        }
        var panel5 =  panel.add('panel')
        for(var i=Math.round(array.length/6)*4;i<Math.round(array.length/6)*5;i++){
            panel5.add('checkbox',undefined,array[i][1])
        }
        var panel6 =  panel.add('panel')
        for(var i=Math.round(array.length/6)*5;i<Math.round(array.length);i++){
            panel6.add('checkbox',undefined,array[i][1])
        }
        panel1.alignChildren=panel2.alignChildren=panel3.alignChildren=panel3.alignChildren=panel4.alignChildren=panel5.alignChildren=panel6.alignChildren='left'    
    var panel_ = panelgroup.add('group')
        panel_.orientation='row'
        var panel_x = panel_.add('checkbox',undefined,'All Countries')
        var panel_xx = panel_.add('checkbox',undefined,'Create Folder')

var gCP = myWindow.add('group')
    gCP.orientation = 'row'
    gCP.alignChildren = 'left'
    var Cptext1 = gCP.add('statictext',undefined,'Campaign Name')
    var Cptext2 = gCP.add('edittext',undefined,cpName)
        Cptext2.characters = 42
var g0 = myWindow.add('group')
    g0.orientation = 'row'
    g0.alignChildren = 'left'
    var staT1 = g0.add('statictext',undefined,'Prefix')
    // var staT2 = g0.add('statictext',undefined,'Country Name')
    var staT3 = g0.add('statictext',undefined,'File Name')

    staT1.characters=12
    // staT2.characters=12
    staT3.characters=33    
var g1 = myWindow.add('group')
    g1.orientation = 'row'
    g1.alignChildren = 'left'
    var text1 = g1.add('edittext',undefined,'')
    // var text2 = g1.add('edittext',undefined,'')
    var text3 = g1.add('edittext',undefined,cpName)//campaign name
    text1.characters=11
    // text2.characters=11
    text3.characters=42
    text1.onChanging = text1.onActivate= text1.onChange = text3.onChanging  = function (){
        text2g2.text = text1.text+'1001'+'_J'+ 'DK'+'_' +text3.text+".indd"
    }



var mypanel= myWindow.add('panel')
var g2 = mypanel.add('group')
    var text1g2 = g2.add('statictext',undefined,'Demo Name:')
    var text2g2 = g2.add('statictext',undefined,text1.text+'1001'+'_J'+ 'DK'+'_' +text3.text+".indd")
        text2g2.characters = 50        
    panel_x.onClick=function(){
        if(panel_x.value==true){
            for (var i =0; i< panel1.children.length; i++){
                panel1.children[i].value=true
                }
            for (var i =0; i< panel2.children.length; i++){
                panel2.children[i].value=true
                }                                                       
            for (var i =0; i< panel3.children.length; i++){
                panel3.children[i].value=true
                }
            for (var i =0; i< panel4.children.length; i++){
                panel4.children[i].value=true
                }                                                       
            for (var i =0; i< panel5.children.length; i++){
                panel5.children[i].value=true
                }
            for (var i =0; i< panel6.children.length; i++){
                panel6.children[i].value=true
                }                                           
            }       
        if(panel_x.value==false){
            for (var i =0; i< panel1.children.length; i++){
                panel1.children[i].value=false
                }
            for (var i =0; i< panel2.children.length; i++){
                panel2.children[i].value=false
                }
            for (var i =0; i< panel3.children.length; i++){
                panel3.children[i].value=false
                }
            for (var i =0; i< panel4.children.length; i++){
                panel4.children[i].value=false
                }
            for (var i =0; i< panel5.children.length; i++){
                panel5.children[i].value=false
                }
            for (var i =0; i< panel6.children.length; i++){
                panel6.children[i].value=false
                }
            }

        }                
    for(h=0;h<panel2.children.length;h++){  
        panel2.children[h].onClick=panel1.children[h].onClick=panel3.children[h].onClick=panel4.children[h].onClick=panel5.children[h].onClick=panel6.children[h].onClick=function(){
        var dem1=[];
        var dem2=[];
        var dem3=[];
        var dem4=[];
        var dem5=[];
        var dem6=[];
        for(var b=0;b<panel1.children.length;b++){
            if(panel1.children[b].value==true){
                dem1.push(b)                     
                }
            }    
        for(var a=0;a<panel2.children.length;a++){
            if(panel2.children[a].value==true){
                dem2.push(a)            
                }
            }
        for(var a=0;a<panel3.children.length;a++){
            if(panel3.children[a].value==true){
                dem3.push(a)            
                }
            }
        for(var a=0;a<panel4.children.length;a++){
            if(panel4.children[a].value==true){
                dem4.push(a)            
                }
            }
        for(var a=0;a<panel5.children.length;a++){
            if(panel5.children[a].value==true){
                dem5.push(a)            
                }
            }
        for(var a=0;a<panel6.children.length;a++){
            if(panel6.children[a].value==true){
                dem6.push(a)            
                }
            }          
        if(dem1.length==panel1.children.length && dem2.length==panel2.children.length && dem3.length==panel3.children.length && dem4.length==panel4.children.length && dem5.length==panel5.children.length && dem6.length==panel6.children.length){                
                panel_x.value=true
            }          
        for(var h=0;h<panel1.children.length;h++){
            if(panel1.children[h].value==false){
                panel_x.value=false
                }                               
            }
        for(var h=0;h<panel2.children.length;h++){
            if(panel2.children[h].value==false){
                panel_x.value=false
                }                               
            }
        for(var h=0;h<panel3.children.length;h++){
            if(panel3.children[h].value==false){
                panel_x.value=false
                }                               
            }
        for(var h=0;h<panel4.children.length;h++){
            if(panel4.children[h].value==false){
                panel_x.value=false
                }                               
            }
        for(var h=0;h<panel5.children.length;h++){
            if(panel5.children[h].value==false){
                panel_x.value=false
                }                               
            }
        for(var h=0;h<panel6.children.length;h++){
            if(panel6.children[h].value==false){
                panel_x.value=false
                }                               
            }                        
        }
    }           
var myButtonGroup = myWindow.add('group');
    myButtonGroup.orientation='row';
    myButtonGroup.add('button',undefined,'OK');
    myButtonGroup.add('button',undefined,'Cancel');
var result = myWindow.show()
if(result==true){
    if(panel_x.value==true){
        for(var k=0;k<array.length;k++){              
            if(panel_xx.value==true){
                var newFolder = new Folder(thePath+"/"+array[k][1])
                newFolder = createfolder(newFolder)
                doc.saveACopy(Folder(thePath+"/"+array[k][1]+"/"+text1.text+array[k][0]+"_J"+array[k][1]+"_"+text3.text+".indd"))
                }
            else{       
                doc.saveACopy(Folder(thePath+"/"+text1.text+array[k][0]+"_J"+array[k][1]+"_"+text3.text+".indd"))
                }   
            }
        }
    else{      
        for(var l=0;l<panel1.children.length;l++){
            if(panel1.children[l].value==true){
                array1.push(panel1.children[l].text)
            }   
        }    
        for(var l=0;l<panel2.children.length;l++){
            if(panel2.children[l].value==true){
                array1.push(panel2.children[l].text)
            }
        }
        for(var l=0;l<panel3.children.length;l++){
            if(panel3.children[l].value==true){
                array1.push(panel3.children[l].text)
            }   
        }    
        for(var l=0;l<panel4.children.length;l++){
            if(panel4.children[l].value==true){
                array1.push(panel4.children[l].text)
            }
        }
        for(var l=0;l<panel5.children.length;l++){
            if(panel5.children[l].value==true){
                array1.push(panel5.children[l].text)
            }   
        }    
        for(var l=0;l<panel6.children.length;l++){
            if(panel6.children[l].value==true){
                array1.push(panel6.children[l].text)
            }
        }
        for(var h=0;h<array1.length;h++){
            for(var n=0;n<array.length;n++){
                if(array1[h]==array[n][1]){
                    if(panel_xx.value==true){
                        var newFolder = new Folder(thePath+"/"+array[n][1])
                        newFolder.create();
                        doc.saveACopy(Folder(thePath+"/"+array[n][1]+"/"+text1.text+array[n][0]+"_J"+array[n][1]+"_"+text3.text+".indd"))
                        }
                    else{       
                        doc.saveACopy(Folder(thePath+"/"+text1.text+array[n][0]+"_J"+array[n][1]+"_"+text3.text+".indd"))
                        }
                    }
                }
            }
        }   
    }
alert('Done')

function createfolder(myfolder){
    if(myfolder.exists==false){
        myfolder.create()
    }
    return myfolder
}

file = File("/Volumes/spring-work/JYSK/7_EasyCatalog/Rename Files Instore.text")
file.open("w")
cpName = Cptext2.text
file.writeln(cpName);
file.close();
}













---
title: 显示表行和列
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 49567a8d-b58d-4636-bead-a1f84b4f111d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ee60e64559a0b4163074ddb62ed72c4600c8e03d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774814"
---
# <a name="displaying-table-rows-and-columns"></a>显示表行和列

  
  
**适用于**： Outlook 
  
 属性页面可以使用通讯簿提供程序以便用户能够定义新的电子邮件收件人。 
  
相应的显示表包含四个行，一个用于每个控件。 指示位置的列的值如下所示。
  
|**控件**|**XPOS**|**YPOS**|**DELTAX**|**DELTAY**|
|:-----|:-----|:-----|:-----|:-----|
|显示名称标签  <br/> |14  <br/> |18  <br/> |49  <br/> |8  <br/> |
|显示名称编辑框  <br/> |76  <br/> |16  <br/> |89  <br/> |12  <br/> |
|电子邮件地址标签  <br/> |14  <br/> |42  <br/> |50  <br/> |8  <br/> |
|电子邮件地址编辑框  <br/> |76  <br/> |40  <br/> |89  <br/> |12  <br/> |
|复选框  <br/> |14  <br/> |64  <br/> |90  <br/> |12  <br/> |
   
此下表建议控件的类型、 **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性和标志，其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性的位掩码的相应的值。
  
|**控件**|**类型**|**Flags**|
|:-----|:-----|:-----|
|显示名称标签  <br/> |DTCT_LABEL  <br/> |0  <br/> |
|显示名称编辑框  <br/> |DTCT_EDIT  <br/> |DT_EDITABLE | DT_REQUIRED  <br/> |
|电子邮件地址标签  <br/> |DTCT_LABEL  <br/> |0  <br/> |
|电子邮件地址编辑框  <br/> |DTCT_EDIT  <br/> |DT_EDITABLE | DT_REQUIRED  <br/> |
|复选框  <br/> |DTCT_CHECKBOX  <br/> |DT_EDITABLE  <br/> |
   
最终的表列出了每个控件使用其关联的控件结构的内容。 请注意，每个标签控件的值显示在紧结构的内存中。
  
|**控件**|**结构**|
|:-----|:-----|
|显示名称标签  <br/> |{sizeof(DTBLLABEL)，0}"显示名称:"  <br/> |
|显示名称编辑框  <br/> |{sizeof(DTBLEDIT)，0，80，PR_DISPLAY_NAME}  <br/> |
|电子邮件地址标签  <br/> |{sizeof(DTBLLABEL)，0}"电子邮件地址:"  <br/> |
|电子邮件地址编辑框  <br/> |{sizeof(DTBLEDIT)，0，80，PR_EMAIL_ADDRESS}  <br/> |
|复选框  <br/> |PR_SEND_RICH_INFO  <br/> |
   
> [!NOTE]
> 显示表中不包含**确定**、**取消**和**帮助**按钮。 用户界面可以通过添加控件显示表中没有在对话框中添加上下文。 
  
## <a name="see-also"></a>另请参阅



[显示表实现](display-table-implementation.md)


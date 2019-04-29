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
ms.openlocfilehash: f9f1cc0bebf3c90a5c12f2714e8ab7eea59104da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407114"
---
# <a name="displaying-table-rows-and-columns"></a>显示表行和列

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 通讯簿提供程序可以使用属性页来使用户能够定义新的电子邮件收件人。 
  
对应的显示表包含四行, 每个控件一个。 指示位置的列的值如下所示。
  
|**Control**|**XPOS**|**YPOS**|**DELTAX**|**DELTAY**|
|:-----|:-----|:-----|:-----|:-----|
|"显示名称" 标签  <br/> |14   <br/> |18  <br/> |49  <br/> |utf-8  <br/> |
|"显示名称" 编辑框  <br/> |76  <br/> |16   <br/> |89  <br/> |12   <br/> |
|电子邮件地址标签  <br/> |14   <br/> |42  <br/> |50  <br/> |utf-8  <br/> |
|"电子邮件地址" 编辑框  <br/> |76  <br/> |40  <br/> |89  <br/> |12   <br/> |
|复选框  <br/> |14   <br/> |64  <br/> |90  <br/> |12   <br/> |
   
下一个表为控件的类型、其**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性和 flags 的位掩码 ( **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性) 提供了相应的值。
  
|**Control**|**Type**|**Flags**|
|:-----|:-----|:-----|
|"显示名称" 标签  <br/> |DTCT_LABEL  <br/> |0  <br/> |
|"显示名称" 编辑框  <br/> |DTCT_EDIT  <br/> |DT_EDITABLE | DT_REQUIRED  <br/> |
|电子邮件地址标签  <br/> |DTCT_LABEL  <br/> |0  <br/> |
|"电子邮件地址" 编辑框  <br/> |DTCT_EDIT  <br/> |DT_EDITABLE | DT_REQUIRED  <br/> |
|复选框  <br/> |DTCT_CHECKBOX  <br/> |DT_EDITABLE  <br/> |
   
最终表格列出了每个控件及其关联的控制结构的内容。 请注意, 每个标签控件的值将直接出现在内存中的结构后面。
  
|**Control**|**结构**|
|:-----|:-----|
|"显示名称" 标签  <br/> |{sizeof (DTBLLABEL), 0}"显示名称:"  <br/> |
|"显示名称" 编辑框  <br/> |{sizeof (DTBLEDIT)、0、80、PR_DISPLAY_NAME}  <br/> |
|电子邮件地址标签  <br/> |{sizeof (DTBLLABEL), 0}"电子邮件地址:"  <br/> |
|"电子邮件地址" 编辑框  <br/> |{sizeof (DTBLEDIT)、0、80、PR_EMAIL_ADDRESS}  <br/> |
|复选框  <br/> |PR_SEND_RICH_INFO  <br/> |
   
> [!NOTE]
> **"确定**"、"**取消**" 和 "**帮助**" 按钮不包含在显示表中。 用户界面可以通过添加不在显示表中的控件, 向对话框添加上下文。 
  
## <a name="see-also"></a>另请参阅



[显示表实现](display-table-implementation.md)


---
title: REPLACE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60108
localization_priority: Normal
ms.assetid: 70c9fc1d-6e7b-479f-effd-0d4bc8ae0f72
description: 根据指定的字符数，将文本字符串的部分用其他文本字符串替换。
ms.openlocfilehash: 75a156d720ca276e75fccf932124ae905e4350b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414352"
---
# <a name="replace-function-visioshapesheet"></a>REPLACE 函数 (VisioShapeSheet)

根据指定的字符数，将文本字符串的部分用其他文本字符串替换。
  
## <a name="syntax"></a>语法

REPLACE (** *old_text* **， ** *start_num* **， ** *num_chars* **， ** *new_text* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _old_text_ <br/> |必需  <br/> |**String** <br/> |要替换其中的一些字符的文本。  <br/> |
| _start_num_ <br/> |必需  <br/> |**Number** <br/> |字符在要替换为 _old_text_ 中 _的位置new_text。_ 字符串中的第一个字符处于位置 1。  <br/> |
| _num_chars_ <br/> |必需  <br/> |**Number** <br/> |要  _替换old_text中的_ 字符数  <br/> |
| _new_text_ <br/> |必需  <br/> |**String** <br/> |将替换中  _字符的文本_ old_text。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

要替换出现在文本字符串中的特定位置的文本时，请使用 REPLACE 函数。如果想要替换文本字符串中的特定文本，则请使用 SUBSTITUTE 函数。
  
## <a name="example"></a>示例

REPLACE ("01/03/2002",9,2,"03") 
  
返回 01/03/2003。 
  


---
title: IConverterSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession
api_type:
- COM
ms.assetid: 24f7a14a-aa6f-4045-054b-4a7aefef25e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a89b1a93b2b03f97426a3988739e9b0d8411f113
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775295"
---
# <a name="iconvertersession--iunknown"></a>IConverterSession : IUnknown

  
  
**适用于**： Outlook 
  
允许 MIME 对象和 MAPI 邮件之间的转换。 这可以是中可在 internet 传输邮件。
  
|||
|:-----|:-----|
|提供者：  <br/> |CLSID_IConverterSession  <br/> |
|接口标识符：  <br/> |IID_IConverterSession  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|**[SetAdrBook](iconvertersession-setadrbook.md)** <br/> |指定到 MIME 转换器 MAPI 解析不明确的地址，将 MAPI 邮件转换为 MIME 流时使用可选 MAPI 通讯簿。  <br/> |
|**[SetEncoding](iconvertersession-setencoding.md)** <br/> |初始化转换期间使用的编码。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|**[MIMEToMAPI](iconvertersession-mimetomapi.md)** <br/> |将 MIME 流转换为 MAPI 邮件。  <br/> |
|**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)** <br/> |将 MAPI 邮件转换为 MIME 流。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|**[SetTextWrapping](iconvertersession-settextwrapping.md)** <br/> |设置的文字环绕转换器返回中**MAPIToMIMEStm**MIME 流宽度。  <br/> |
|**[SetSaveFormat](iconvertersession-setsaveformat.md)** <br/> |转换器的返回中**MAPIToMIMEStm**MIME 流的格式设置。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|**[SetCharSet](iconvertersession-setcharset.md)** <br/> |指定一个可选的字符设置为 MIME 转换器 MAPI 使用将 MAPI 邮件转换为 MIME 流时。  <br/> |
   
## <a name="remarks"></a>说明

使用**MAPIToMIMEStm**执行转换之前调用**SetEncoding** 。 
  
## <a name="see-also"></a>另请参阅



[关于 MAPI-MIME 转换 API](about-the-mapi-mime-conversion-api.md)
  
[MAPI 常量](mapi-constants.md)


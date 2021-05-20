---
title: OpenStreamOnFile
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenStreamOnFile
api_type:
- COM
ms.assetid: 01fa459f-597d-4b16-b340-a79fb270cd71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b05f5b30eceb7df1bed76c64f4bdda87ede0e463
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439091"
---
# <a name="openstreamonfile"></a>OpenStreamOnFile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
分配和初始化 OLE **IStream** 对象以访问文件的内容。 此函数采用 ANSI 字符串作为文件名，包括路径和文件扩展名，因此建议使用此函数的 Unicode 版本[OpenStreamOnFileW。](openstreamonfilew.md)
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT STDMETHODCALLTYPE OpenStreamOnFile(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  LPSTR lpszFileName,
  LPSTR lpszPrefix,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _ulFlags_
  
> [in]用于控制要通过 OLE **IStream** 对象访问的文件的创建或打开的标志的位掩码。 可以设置以下标志： 
    
SOF_UNIQUEFILENAME 
  
> 为 **IStream** 对象创建临时文件。 如果设置此标志，则STGM_CREATE和STGM_READWRITE标记。 
    
STGM_CREATE 
  
> 即使文件已存在，也创建该文件。 如果未设置  _lpszFileName_ 参数，则必须同时设置此STGM_DELETEONRELEASE和属性。 如果STGM_CREATE，则还必须STGM_READWRITE标记。 
    
STGM_DELETEONRELEASE 
  
> 释放 **IStream** 对象时将删除该文件。 如果未设置  _lpszFileName_ 参数，则必须同时设置此STGM_CREATE和属性。 
    
STGM_READ 
  
> 文件将创建或打开，具有只读访问权限。 
    
STGM_READWRITE 
  
> 文件是使用读/写权限创建或打开的。 如果未设置此标志，则STGM_CREATE设置此标志。 
    
 _lpszFileName_
  
> [in]Filename， including path and extension， of the file for which **OpenStreamOnFile** initializes the **IStream** object. 如果  _SOF_UNIQUEFILENAME，lpszFileName_ 将包含用于创建临时文件的目录的路径。 如果  _lpszFileName_ 为 **NULL，OpenStreamOnFile** 从系统获取相应的路径，并且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。 
    
 _lpszPrefix_
  
> [in] **OpenStreamOnFile** 初始化 **IStream** 对象的文件名的前缀。 如果设置，则前缀不能超过三个字符。 如果  _lpszPrefix_ 为 NULL，则使用前缀"SOF"。 
    
 _lppStream_
  
> [out]指向公开 **IStream** 接口的对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_NO_ACCESS 
  
> 由于用户权限不足或无法修改只读文件，无法访问该文件。 
    
MAPI_E_NOT_FOUND 
  
> 指定的文件不存在。
    
## <a name="remarks"></a>备注

**OpenStreamOnFile** 函数有两个重要用途，通过设置 SOF_UNIQUEFILENAME 可区分。 未设置此标志时 **，OpenStreamOnFile** 将打开现有文件的 IStream 对象，例如，使用 **IStream：：CopyTo** 方法将其内容复制到附件的 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。  在这种情况下  _，lpszFileName_ 参数指定文件的路径和文件名。 
  
当SOF_UNIQUEFILENAME时 **，OpenStreamOnFile** 会创建一个临时文件来保存 **IStream 对象** 的数据。 对于此用法  _，lpszFileName_ 参数可以选择指定要创建文件的目录的路径  _，lpszPrefix_ 参数还可以选择指定文件名的前缀。 
  
当调用客户端应用程序或服务提供商使用 **IStream** 对象完成时，它应通过调用 OLE **IStream：：Release** 方法释放它。 
  
MAPI 使用  _lpAllocateBuffer_ 和  _lpFreeBuffer_ 指向的函数进行大部分内存分配和处理，尤其是分配内存，供客户端应用程序在调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时使用。 
  
## <a name="notes-to-callers"></a>给调用方的说明

the SOF_UNIQUEFILENAME flag is used to create a temporary file with a name unique to the messaging system. 如果设置此标志，则  _lpszFileName_ 参数指定临时文件的路径，  _并且 lpszPrefix_ 参数包含文件名的前缀字符。 构造的文件名为 <prefix> HHHH。TMP，其中 HHHH 是十六进制数。 如果 _lpszFileName_ 为 NULL，将在从 Windows 函数 **GetTempPath** 返回的临时文件目录中创建文件，如果尚未指定临时文件目录，则在当前目录中创建该文件。 
  
如果未SOF_UNIQUEFILENAME，_则忽略 lpszPrefix，lpszFileName_ 应包含要打开或创建的文件的完全限定路径和文件名。 文件将基于  _ulFlags_ 中设置的其他标志打开或创建。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |WriteAttachStreamToFile  <br/> |MFCMAPI 使用 **OpenStreamOnFile** 方法打开文件上的流，以便可以将附件写入文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)


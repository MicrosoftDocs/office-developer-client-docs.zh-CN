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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348627"
---
# <a name="openstreamonfile"></a><span data-ttu-id="85282-103">OpenStreamOnFile</span><span class="sxs-lookup"><span data-stu-id="85282-103">OpenStreamOnFile</span></span>

  
  
<span data-ttu-id="85282-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85282-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85282-105">分配并初始化 OLE **IStream**对象以访问文件的内容。</span><span class="sxs-lookup"><span data-stu-id="85282-105">Allocates and initializes an OLE **IStream** object to access the contents of a file.</span></span> <span data-ttu-id="85282-106">此函数采用 ANSI 字符串作为文件名, 包括路径和文件扩展名, 因此, 建议使用此函数的 Unicode 版本[OpenStreamOnFileW](openstreamonfilew.md)。</span><span class="sxs-lookup"><span data-stu-id="85282-106">This function takes an ANSI string as the file name including the path and the file extension, therefore, use of the Unicode version of this function, [OpenStreamOnFileW](openstreamonfilew.md), is recommended.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="85282-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="85282-107">Header file:</span></span>  <br/> |<span data-ttu-id="85282-108">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="85282-108">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="85282-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="85282-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="85282-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="85282-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="85282-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="85282-111">Called by:</span></span>  <br/> |<span data-ttu-id="85282-112">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="85282-112">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="85282-113">参数</span><span class="sxs-lookup"><span data-stu-id="85282-113">Parameters</span></span>

 <span data-ttu-id="85282-114">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="85282-114">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="85282-115">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="85282-115">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="85282-116">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="85282-116">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="85282-117">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="85282-117">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="85282-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="85282-118">_ulFlags_</span></span>
  
> <span data-ttu-id="85282-119">实时用于控制要通过 OLE **IStream**对象访问的文件的创建或打开的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="85282-119">[in] Bitmask of flags used to control the creation or opening of the file to be accessed through the OLE **IStream** object.</span></span> <span data-ttu-id="85282-120">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="85282-120">The following flags can be set:</span></span> 
    
<span data-ttu-id="85282-121">SOF_UNIQUEFILENAME</span><span class="sxs-lookup"><span data-stu-id="85282-121">SOF_UNIQUEFILENAME</span></span> 
  
> <span data-ttu-id="85282-122">将为**IStream**对象创建一个临时文件。</span><span class="sxs-lookup"><span data-stu-id="85282-122">A temporary file is to be created for the **IStream** object.</span></span> <span data-ttu-id="85282-123">如果设置了此标志, 则还应设置 STGM_CREATE 和 STGM_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="85282-123">If this flag is set, the STGM_CREATE and STGM_READWRITE flags should also be set.</span></span> 
    
<span data-ttu-id="85282-124">STGM_CREATE</span><span class="sxs-lookup"><span data-stu-id="85282-124">STGM_CREATE</span></span> 
  
> <span data-ttu-id="85282-125">即使已经存在文件, 也要创建文件。</span><span class="sxs-lookup"><span data-stu-id="85282-125">The file is to be created even if one already exists.</span></span> <span data-ttu-id="85282-126">如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_DELETEONRELEASE。</span><span class="sxs-lookup"><span data-stu-id="85282-126">If the  _lpszFileName_ parameter is not set, both this flag and STGM_DELETEONRELEASE must be set.</span></span> <span data-ttu-id="85282-127">如果设置了 STGM_CREATE, 则还必须设置 STGM_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="85282-127">If STGM_CREATE is set, the STGM_READWRITE flag must also be set.</span></span> 
    
<span data-ttu-id="85282-128">STGM_DELETEONRELEASE</span><span class="sxs-lookup"><span data-stu-id="85282-128">STGM_DELETEONRELEASE</span></span> 
  
> <span data-ttu-id="85282-129">释放**IStream**对象时, 将删除该文件。</span><span class="sxs-lookup"><span data-stu-id="85282-129">The file is to be deleted when the **IStream** object is released.</span></span> <span data-ttu-id="85282-130">如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_CREATE。</span><span class="sxs-lookup"><span data-stu-id="85282-130">If the  _lpszFileName_ parameter is not set, both this flag and STGM_CREATE must be set.</span></span> 
    
<span data-ttu-id="85282-131">STGM_READ</span><span class="sxs-lookup"><span data-stu-id="85282-131">STGM_READ</span></span> 
  
> <span data-ttu-id="85282-132">将使用只读访问权限创建或打开文件。</span><span class="sxs-lookup"><span data-stu-id="85282-132">The file is to be created or opened with read-only access.</span></span> 
    
<span data-ttu-id="85282-133">STGM_READWRITE</span><span class="sxs-lookup"><span data-stu-id="85282-133">STGM_READWRITE</span></span> 
  
> <span data-ttu-id="85282-134">将使用读/写权限创建或打开文件。</span><span class="sxs-lookup"><span data-stu-id="85282-134">The file is to be created or opened with read/write permission.</span></span> <span data-ttu-id="85282-135">如果未设置此标志, 则不得设置 STGM_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="85282-135">If this flag is not set, the STGM_CREATE flag must not be set either.</span></span> 
    
 <span data-ttu-id="85282-136">_lpszFileName_</span><span class="sxs-lookup"><span data-stu-id="85282-136">_lpszFileName_</span></span>
  
> <span data-ttu-id="85282-137">实时**OpenStreamOnFile**为其初始化**IStream**对象的文件的文件名, 包括路径和扩展名。</span><span class="sxs-lookup"><span data-stu-id="85282-137">[in] The filename, including path and extension, of the file for which **OpenStreamOnFile** initializes the **IStream** object.</span></span> <span data-ttu-id="85282-138">如果设置了 SOF_UNIQUEFILENAME 标志, 则_lpszFileName_包含要在其中创建临时文件的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="85282-138">If the SOF_UNIQUEFILENAME flag is set,  _lpszFileName_ contains the path to the directory in which to create a temporary file.</span></span> <span data-ttu-id="85282-139">如果_lpszFileName_为 NULL, 则**OpenStreamOnFile**从系统中获取适当的路径, 并且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。</span><span class="sxs-lookup"><span data-stu-id="85282-139">If  _lpszFileName_ is NULL, **OpenStreamOnFile** obtains an appropriate path from the system, and both the STGM_CREATE and STGM_DELETEONRELEASE flags must be set.</span></span> 
    
 <span data-ttu-id="85282-140">_lpszPrefix_</span><span class="sxs-lookup"><span data-stu-id="85282-140">_lpszPrefix_</span></span>
  
> <span data-ttu-id="85282-141">实时**OpenStreamOnFile**用于初始化**IStream**对象的文件名的前缀。</span><span class="sxs-lookup"><span data-stu-id="85282-141">[in] The prefix for the filename on which **OpenStreamOnFile** initializes the **IStream** object.</span></span> <span data-ttu-id="85282-142">如果设置, 则前缀必须包含三个以上的字符。</span><span class="sxs-lookup"><span data-stu-id="85282-142">If set, the prefix must contain not more than three characters.</span></span> <span data-ttu-id="85282-143">如果_lpszPrefix_为 NULL, 则使用前缀 "SOF"。</span><span class="sxs-lookup"><span data-stu-id="85282-143">If  _lpszPrefix_ is NULL, a prefix of "SOF" is used.</span></span> 
    
 <span data-ttu-id="85282-144">_lppStream_</span><span class="sxs-lookup"><span data-stu-id="85282-144">_lppStream_</span></span>
  
> <span data-ttu-id="85282-145">排除指向公开**IStream**接口的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="85282-145">[out] Pointer to a pointer to an object exposing the **IStream** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="85282-146">返回值</span><span class="sxs-lookup"><span data-stu-id="85282-146">Return value</span></span>

<span data-ttu-id="85282-147">S_OK</span><span class="sxs-lookup"><span data-stu-id="85282-147">S_OK</span></span> 
  
> <span data-ttu-id="85282-148">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="85282-148">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="85282-149">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="85282-149">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="85282-150">由于用户权限不足或无法修改只读文件, 无法访问文件。</span><span class="sxs-lookup"><span data-stu-id="85282-150">The file could not be accessed due to insufficient user permissions or because read-only files cannot be modified.</span></span> 
    
<span data-ttu-id="85282-151">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="85282-151">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="85282-152">指定的文件不存在。</span><span class="sxs-lookup"><span data-stu-id="85282-152">The designated file does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="85282-153">注解</span><span class="sxs-lookup"><span data-stu-id="85282-153">Remarks</span></span>

<span data-ttu-id="85282-154">**OpenStreamOnFile**函数有两个重要的用途, 它们由 SOF_UNIQUEFILENAME 标志的设置加以区分。</span><span class="sxs-lookup"><span data-stu-id="85282-154">The **OpenStreamOnFile** function has two important uses, distinguished by the setting of the SOF_UNIQUEFILENAME flag.</span></span> <span data-ttu-id="85282-155">如果未设置此标志, 则**OpenStreamOnFile**将在现有文件上打开**IStream**对象, 例如将其内容复制到使用 IStream 的附件的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。 **:: CopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="85282-155">When this flag is not set, **OpenStreamOnFile** opens an **IStream** object on an existing file, for example to copy its contents to the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property of an attachment using the **IStream::CopyTo** method.</span></span> <span data-ttu-id="85282-156">在这种情况下, _lpszFileName_参数指定文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="85282-156">In this case the  _lpszFileName_ parameter specifies the path and filename of the file.</span></span> 
  
<span data-ttu-id="85282-157">设置 SOF_UNIQUEFILENAME 后, **OpenStreamOnFile**将创建一个临时文件, 用于保存**IStream**对象的数据。</span><span class="sxs-lookup"><span data-stu-id="85282-157">When SOF_UNIQUEFILENAME is set, **OpenStreamOnFile** creates a temporary file to hold data for an **IStream** object.</span></span> <span data-ttu-id="85282-158">在此用法中, _lpszFileName_参数可以选择指定要在其中创建文件的目录的路径, 并且_lpszPrefix_参数可以选择为文件名指定前缀。</span><span class="sxs-lookup"><span data-stu-id="85282-158">For this usage, the  _lpszFileName_ parameter can optionally designate the path to the directory where the file is to be created, and the  _lpszPrefix_ parameter can optionally specify a prefix for the filename.</span></span> 
  
<span data-ttu-id="85282-159">当调用客户端应用程序或服务提供程序完成了**IStream**对象时, 它应通过调用 OLE **IStream:: Release**方法来释放它。</span><span class="sxs-lookup"><span data-stu-id="85282-159">When the calling client application or service provider is finished with the **IStream** object, it should free it by calling the OLE **IStream::Release** method.</span></span> 
  
<span data-ttu-id="85282-160">MAPI 使用_lpAllocateBuffer_和_lpFreeBuffer_指向的函数来实现大多数内存分配和释放, 尤其是在调用对象接口 (如[IMAPIProp::) 时分配供客户端应用程序使用的内存。GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="85282-160">MAPI uses the functions pointed to by  _lpAllocateBuffer_ and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="85282-161">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="85282-161">Notes to callers</span></span>

<span data-ttu-id="85282-162">SOF_UNIQUEFILENAME 标志用于创建具有邮件系统特有名称的临时文件。</span><span class="sxs-lookup"><span data-stu-id="85282-162">The SOF_UNIQUEFILENAME flag is used to create a temporary file with a name unique to the messaging system.</span></span> <span data-ttu-id="85282-163">如果设置了此标志, 则_lpszFileName_参数指定临时文件的路径, _lpszPrefix_参数包含文件名的前缀字符。</span><span class="sxs-lookup"><span data-stu-id="85282-163">If this flag is set, the  _lpszFileName_ parameter specifes the path for the temporary file, and the  _lpszPrefix_ parameter contains the prefix characters of the filename.</span></span> <span data-ttu-id="85282-164">构造的文件名为<prefix>HHHH。TMP, 其中 HHHH 是一个十六进制数。</span><span class="sxs-lookup"><span data-stu-id="85282-164">The constructed filename is <prefix>HHHH.TMP, where HHHH is a hexadecimal number.</span></span> <span data-ttu-id="85282-165">如果_lpszFileName_为 NULL, 则将在从 Windows 函数**GetTempPath**返回的临时文件目录中创建文件; 如果未指定临时文件目录, 则将在当前目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="85282-165">If  _lpszFileName_ is NULL, the file will be created in the temporary file directory that is returned from the Windows function **GetTempPath**, or the current directory if no temporary file directory has been designated.</span></span> 
  
<span data-ttu-id="85282-166">如果未设置 SOF_UNIQUEFILENAME 标志, 则将忽略_lpszPrefix_ , 并且_lpszFileName_应包含要打开或创建的文件的完全限定路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="85282-166">If the SOF_UNIQUEFILENAME flag is not set,  _lpszPrefix_ is ignored, and  _lpszFileName_ should contain the fully qualified path and filename of the file to be opened or created.</span></span> <span data-ttu-id="85282-167">将根据在_ulFlags_中设置的其他标志打开或创建文件。</span><span class="sxs-lookup"><span data-stu-id="85282-167">The file will be opened or created based on the other flags that are set in  _ulFlags_.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="85282-168">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="85282-168">MFCMAPI reference</span></span>

<span data-ttu-id="85282-169">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="85282-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="85282-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="85282-170">**File**</span></span>|<span data-ttu-id="85282-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="85282-171">**Function**</span></span>|<span data-ttu-id="85282-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="85282-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85282-173">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="85282-173">File.cpp</span></span>  <br/> |<span data-ttu-id="85282-174">WriteAttachStreamToFile</span><span class="sxs-lookup"><span data-stu-id="85282-174">WriteAttachStreamToFile</span></span>  <br/> |<span data-ttu-id="85282-175">MFCMAPI 使用**OpenStreamOnFile**方法打开文件上的流, 以便可以向其写入附件。</span><span class="sxs-lookup"><span data-stu-id="85282-175">MFCMAPI uses the **OpenStreamOnFile** method to open a stream on a file so an attachment can be written out to it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="85282-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85282-176">See also</span></span>



[<span data-ttu-id="85282-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="85282-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)


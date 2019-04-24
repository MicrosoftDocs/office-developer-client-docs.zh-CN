---
title: IAddrBookSetDefaultDir
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetDefaultDir
api_type:
- COM
ms.assetid: d5d60150-15e4-41ff-bfb0-0c67e2abcacc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ab01f189734ac30b4c027f4e5596c88031b5f99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341697"
---
# <a name="iaddrbooksetdefaultdir"></a><span data-ttu-id="6ec5a-103">IAddrBook::SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="6ec5a-103">IAddrBook::SetDefaultDir</span></span>

  
  
<span data-ttu-id="6ec5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6ec5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6ec5a-105">将指定的容器建立为默认的通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-105">Establishes the specified container as the default address book container.</span></span>
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="6ec5a-106">参数</span><span class="sxs-lookup"><span data-stu-id="6ec5a-106">Parameters</span></span>

 <span data-ttu-id="6ec5a-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="6ec5a-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="6ec5a-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="6ec5a-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="6ec5a-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="6ec5a-110">实时指向默认通讯簿容器的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-110">[in] A pointer to the entry identifier of the default address book container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6ec5a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6ec5a-111">Return value</span></span>

<span data-ttu-id="6ec5a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ec5a-112">S_OK</span></span> 
  
> <span data-ttu-id="6ec5a-113">已成功设置默认的通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-113">The default address book container was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6ec5a-114">注解</span><span class="sxs-lookup"><span data-stu-id="6ec5a-114">Remarks</span></span>

<span data-ttu-id="6ec5a-115">客户端和服务提供程序调用**SetDefaultDir**方法以建立新的默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-115">Clients and service providers call the **SetDefaultDir** method to establish a new default address book container.</span></span> <span data-ttu-id="6ec5a-116">默认容器是首次打开通讯簿时用户看到的在通讯簿中显示的容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-116">The default container is the container that the user sees displayed in the address book when the address book is first opened.</span></span> <span data-ttu-id="6ec5a-117">**SetDefaultDir**将默认容器保存为配置文件中的条目。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-117">**SetDefaultDir** saves the default container as an entry in the profile.</span></span> <span data-ttu-id="6ec5a-118">容器将一直保留为默认值, 直到在同一会话中或在另一个会话中对**SetDefaultDir**进行了另一个调用, 或者删除了容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-118">The container remains as the default until either another call to **SetDefaultDir** is made in the same session or in another session, or the container is removed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ec5a-119">[PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性对应于 "通讯簿选项" 对话框中的 "**自动选择**" 设置。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-119">The [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property corresponds to the **Choose automatically** setting in the Address Book Options dialog.</span></span> <span data-ttu-id="6ec5a-120">当[IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件部分中存在此属性并将其设置为**true**时, 通讯簿对话框不再默认为**SetDefaultDir**指定的容器, 而是选择 Microsoft Outlook 认为的通讯簿适合在其中显示对话框的上下文。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-120">When this property exists in the [IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx) profile section and is set to **true**, the Address Book dialog no longer defaults to the container specified by **SetDefaultDir**, but chooses an address book that Microsoft Outlook considers appropriate for the context in which the dialog was displayed.</span></span> <span data-ttu-id="6ec5a-121">请注意, 这可能会导致第三方通讯簿提供程序的体验不佳。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-121">Note that this may result in a poor experience for third-party address book providers.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6ec5a-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6ec5a-122">MFCMAPI reference</span></span>

<span data-ttu-id="6ec5a-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6ec5a-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="6ec5a-124">**File**</span></span>|<span data-ttu-id="6ec5a-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="6ec5a-125">**Function**</span></span>|<span data-ttu-id="6ec5a-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="6ec5a-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ec5a-127">Abcontdlg</span><span class="sxs-lookup"><span data-stu-id="6ec5a-127">Abcontdlg.cpp</span></span>  <br/> |<span data-ttu-id="6ec5a-128">CAbContDlg:: OnSetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="6ec5a-128">CAbContDlg::OnSetDefaultDir</span></span>  <br/> |<span data-ttu-id="6ec5a-129">MFCMAPI 使用**SetDefaultDir**方法将指定的通讯簿容器设为默认容器。</span><span class="sxs-lookup"><span data-stu-id="6ec5a-129">MFCMAPI uses the **SetDefaultDir** method to make the specified address book container the default one.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6ec5a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec5a-130">See also</span></span>



[<span data-ttu-id="6ec5a-131">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="6ec5a-131">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="6ec5a-132">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="6ec5a-132">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="6ec5a-133">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="6ec5a-133">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
  
[<span data-ttu-id="6ec5a-134">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="6ec5a-134">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="6ec5a-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6ec5a-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="6ec5a-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6ec5a-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)


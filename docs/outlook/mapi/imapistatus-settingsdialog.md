---
title: IMAPIStatusSettingsDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.SettingsDialog
api_type:
- COM
ms.assetid: e931246e-7fff-4116-a9fc-f685988e21e8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e9d390a895490f2f7445c5f1ed6e0bde3a87639
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331540"
---
# <a name="imapistatussettingsdialog"></a><span data-ttu-id="a298a-103">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="a298a-103">IMAPIStatus::SettingsDialog</span></span>

  
  
<span data-ttu-id="a298a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a298a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a298a-105">显示允许用户更改服务提供程序配置的属性表。 MAPI 实现的 status 对象中不支持此方法。</span><span class="sxs-lookup"><span data-stu-id="a298a-105">Displays a property sheet that enables the user to change a service provider's configuration This method is not supported in status objects that MAPI implements.</span></span>
  
```cpp
HRESULT SettingsDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a298a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a298a-106">Parameters</span></span>

 <span data-ttu-id="a298a-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a298a-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="a298a-108">实时配置属性表的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a298a-108">[in] A handle to the parent window of the configuration property sheet.</span></span>
    
 <span data-ttu-id="a298a-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a298a-109">_ulFlags_</span></span>
  
> <span data-ttu-id="a298a-110">实时用于控制属性表的显示的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a298a-110">[in] A bitmask of flags that controls the display of the property sheet.</span></span> <span data-ttu-id="a298a-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a298a-111">The following flag can be set:</span></span>
    
<span data-ttu-id="a298a-112">UI_READONLY</span><span class="sxs-lookup"><span data-stu-id="a298a-112">UI_READONLY</span></span> 
  
> <span data-ttu-id="a298a-113">建议提供程序不应使用户能够更改配置属性。</span><span class="sxs-lookup"><span data-stu-id="a298a-113">Suggests that the provider should not enable users to change configuration properties.</span></span> <span data-ttu-id="a298a-114">此标志只是一个建议;可以忽略它。</span><span class="sxs-lookup"><span data-stu-id="a298a-114">This flag is only a suggestion; it can be ignored.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a298a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a298a-115">Return value</span></span>

<span data-ttu-id="a298a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a298a-116">S_OK</span></span> 
  
> <span data-ttu-id="a298a-117">已成功显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="a298a-117">The configuration property sheet was displayed successfully.</span></span>
    
<span data-ttu-id="a298a-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="a298a-118">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="a298a-119">status 对象不支持此方法, 正如**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中缺少 STATUS_SETTINGS_DIALOG 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="a298a-119">The status object does not support this method, as indicated by the absence of the STATUS_SETTINGS_DIALOG flag in the **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a298a-120">注解</span><span class="sxs-lookup"><span data-stu-id="a298a-120">Remarks</span></span>

<span data-ttu-id="a298a-121">**IMAPIStatus:: SettingsDialog**方法显示一个配置属性表。</span><span class="sxs-lookup"><span data-stu-id="a298a-121">The **IMAPIStatus::SettingsDialog** method displays a configuration property sheet.</span></span> <span data-ttu-id="a298a-122">所有服务提供程序都应支持**SettingsDialog**方法, 但这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a298a-122">All service providers should support the **SettingsDialog** method, but it is not required.</span></span> <span data-ttu-id="a298a-123">服务提供程序可以实现自己的属性表, 也可以使用支持对象的 IMAPISupport 中提供的实现[::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a298a-123">Service providers can implement their own property sheets or use the implementation supplied in the support object's [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method.</span></span> <span data-ttu-id="a298a-124">**DoConfigPropsheet**生成读/写属性表。</span><span class="sxs-lookup"><span data-stu-id="a298a-124">**DoConfigPropsheet** builds a read/write property sheet.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a298a-125">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a298a-125">Notes to implementers</span></span>

<span data-ttu-id="a298a-126">如果远程传输提供程序具有任何设置, 则应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a298a-126">If a remote transport provider has any settings, it should do the following:</span></span>
  
- <span data-ttu-id="a298a-127">打开传输提供程序的 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="a298a-127">Open the transport provider's profile section.</span></span>
    
- <span data-ttu-id="a298a-128">从配置文件中获取传输提供程序的属性设置。</span><span class="sxs-lookup"><span data-stu-id="a298a-128">Get the transport provider's property settings from the profile.</span></span>
    
- <span data-ttu-id="a298a-129">在对话框中显示属性设置。</span><span class="sxs-lookup"><span data-stu-id="a298a-129">Display the property settings in a dialog box.</span></span>
    
- <span data-ttu-id="a298a-130">如果对话框允许编辑属性设置, 请检查新设置是否有效, 并将其重新存储在传输提供程序的配置文件部分中。</span><span class="sxs-lookup"><span data-stu-id="a298a-130">If the dialog box allows editing of the property settings, check that the new settings are valid and store them back in the transport provider's profile section.</span></span>
    
- <span data-ttu-id="a298a-131">返回 S_OK 或在前面的步骤中返回的任何错误值。</span><span class="sxs-lookup"><span data-stu-id="a298a-131">Return S_OK, or any error values returned during the preceding steps.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="a298a-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a298a-132">Notes to callers</span></span>

<span data-ttu-id="a298a-133">您可以使用通过**SettingsDialog**显示的属性表执行各种任务, 如以下操作:</span><span class="sxs-lookup"><span data-stu-id="a298a-133">You can use the property sheet displayed through **SettingsDialog** to perform a variety of tasks, such as the following:</span></span> 
  
- <span data-ttu-id="a298a-134">指定默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="a298a-134">Specify a default message store.</span></span>
    
- <span data-ttu-id="a298a-135">指定传输顺序。</span><span class="sxs-lookup"><span data-stu-id="a298a-135">Specify a transport order.</span></span>
    
- <span data-ttu-id="a298a-136">指定用于浏览的默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="a298a-136">Specify a default address book container for browsing.</span></span>
    
- <span data-ttu-id="a298a-137">指定用于解析不明确名称的搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="a298a-137">Specify a search order for resolving ambiguous names.</span></span>
    
- <span data-ttu-id="a298a-138">指定默认的个人通讯簿。</span><span class="sxs-lookup"><span data-stu-id="a298a-138">Specify a default personal address book.</span></span>
    
<span data-ttu-id="a298a-139">服务提供程序可以实现可读写、只读或混合权限的属性表, 具体取决于属性。</span><span class="sxs-lookup"><span data-stu-id="a298a-139">Service providers can implement property sheets that are read/write, read-only, or a mixture of permissions, depending on the property.</span></span> <span data-ttu-id="a298a-140">服务提供程序可以通过设置属性限制对各个属性实现不同的权限。</span><span class="sxs-lookup"><span data-stu-id="a298a-140">Service providers can implement different permissions on individual properties by setting property restrictions.</span></span> <span data-ttu-id="a298a-141">属性表的默认模式为 "读/写"。</span><span class="sxs-lookup"><span data-stu-id="a298a-141">The default mode for property sheets is read/write.</span></span> <span data-ttu-id="a298a-142">您可以通过在对**SettingsDialog**的调用中设置 UI_READONLY 标志来请求只读属性表。</span><span class="sxs-lookup"><span data-stu-id="a298a-142">You can request read-only property sheets by setting the UI_READONLY flag in your calls to **SettingsDialog**.</span></span> <span data-ttu-id="a298a-143">能够实现只读属性表的服务提供程序可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a298a-143">Service providers that are able to implement read-only property sheets can do so.</span></span> <span data-ttu-id="a298a-144">但是, 由于某些服务提供程序无法覆盖默认模式, 因此必须准备好处理任一类型的属性表。</span><span class="sxs-lookup"><span data-stu-id="a298a-144">However, because some service providers cannot override the default mode, you must be prepared to handle property sheets of either type.</span></span> 
  
<span data-ttu-id="a298a-145">由于用户界面始终包含在此操作中, 因此只有交互客户端才应调用**SettingsDialog**。</span><span class="sxs-lookup"><span data-stu-id="a298a-145">Because a user interface is always involved in this operation, only interactive clients should call **SettingsDialog**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a298a-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a298a-146">See also</span></span>



[<span data-ttu-id="a298a-147">IMAPISupport::DoConfigPropsheet</span><span class="sxs-lookup"><span data-stu-id="a298a-147">IMAPISupport::DoConfigPropsheet</span></span>](imapisupport-doconfigpropsheet.md)
  
[<span data-ttu-id="a298a-148">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="a298a-148">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="a298a-149">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a298a-149">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)


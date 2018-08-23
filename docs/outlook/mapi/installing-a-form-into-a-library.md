---
title: 将表单安装到库中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 303c9dcb-f9b5-4cea-b5f2-3eba01aa3b09
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d3b20c9fb4b4f1a26eb4ed1a9a498bd56a915a70
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579779"
---
# <a name="installing-a-form-into-a-library"></a><span data-ttu-id="3b6c7-103">将表单安装到库中</span><span class="sxs-lookup"><span data-stu-id="3b6c7-103">Installing a Form into a Library</span></span>

  
  
<span data-ttu-id="3b6c7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b6c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b6c7-105">与 Windows SDK 一起提供的默认 MAPI 窗体管理器不提供安装在不同的表单库中的窗体的用户界面。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-105">The default MAPI form manager supplied with the Windows SDK does not provide a user interface for installing forms in the various form libraries.</span></span> <span data-ttu-id="3b6c7-106">因此，您将需要创建一个小应用程序 — 或详细说明 — 用户可用来安装该表单。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-106">Because of this, you will have to create a small application — or detailed set of instructions — that users can use to install the form.</span></span>
  
<span data-ttu-id="3b6c7-107">如果实现安装应用程序，操作的一系列它必须执行安装窗体到表如下所示的某个文件夹的相关内容：</span><span class="sxs-lookup"><span data-stu-id="3b6c7-107">If you implement an installation application, the series of actions it must perform to install a form into a folder's associated contents table are as follows:</span></span>
  
1. <span data-ttu-id="3b6c7-108">调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-108">Call the [MAPIOpenFormMgr](mapiopenformmgr.md) function to open the form manager.</span></span> 
    
2. <span data-ttu-id="3b6c7-109">[IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)或[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)方法用于选择并打开窗体的目标容器。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-109">Use [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) or [IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md) method to select and open the target container for the form.</span></span> 
    
3. <span data-ttu-id="3b6c7-110">使用[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)函数安装该表单。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-110">Use the [IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md) function to install the form.</span></span> 
    
    <span data-ttu-id="3b6c7-111">步骤 4 至 6 供安装到本地表单库：</span><span class="sxs-lookup"><span data-stu-id="3b6c7-111">Steps 4 through 6 are for installation into a local form library:</span></span>
    
4. <span data-ttu-id="3b6c7-112">如果安装到用户的工作站上的本地窗体库，将所有文件都复制到本地磁盘上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-112">Copy all files to the appropriate place on the local disk, if installation is to the local form library on the user's workstation.</span></span> <span data-ttu-id="3b6c7-113">如有必要，修改窗体配置文件，以反映当前路径的组件。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-113">If necessary, modify the form configuration file to reflect current paths of components.</span></span> <span data-ttu-id="3b6c7-114">窗体配置文件可以包含的相对路径，在这种情况下此步骤可能不要求。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-114">The form configuration file can contain relative paths, in which case this step may not be necessary.</span></span>
    
5. <span data-ttu-id="3b6c7-115">完成相应的 OLE 注册步骤将邮件类型与所安装的窗体服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-115">Complete the appropriate OLE registration steps to associate the message type with the form server being installed.</span></span>
    
6. <span data-ttu-id="3b6c7-116">如果窗体已安装到本地窗体库中，复制该窗体的图标 (.ico) 和配置 (.cfg) 文件到 %WINDOWS%\FORMS\CONFIGS 目录，以便表单可以自动还原表单库已损坏或已删除的情况下。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-116">If the form was installed into the local form library, copy the form's icon (.ico) and configuration (.cfg) files into the %WINDOWS%\FORMS\CONFIGS directory so the form can be automatically restored in case the form library is corrupted or deleted.</span></span> <span data-ttu-id="3b6c7-117">建议，但不是强制性，此步骤。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-117">This step is recommended but not mandatory.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b6c7-118">通过调用[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数替换为步骤 1 和 2 可以简化安装到本地表单库。</span><span class="sxs-lookup"><span data-stu-id="3b6c7-118">You can simplify installation to a local form library by replacing steps 1 and 2 with a call to the [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3b6c7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b6c7-119">See also</span></span>



[<span data-ttu-id="3b6c7-120">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="3b6c7-120">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)


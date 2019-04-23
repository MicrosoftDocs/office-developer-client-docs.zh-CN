---
title: 将业务对象标记为脚本安全
TOCTitle: Marking business objects as safe for scripting
ms:assetid: 8ee49aec-672d-96f7-baa6-9261317a4d90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249630(v=office.15)
ms:contentKeyID: 48546295
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fe5d331b7f3ab4685cb930323076d111a25ec68e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289775"
---
# <a name="marking-business-objects-as-safe-for-scripting"></a><span data-ttu-id="a15f3-102">将业务对象标记为脚本安全</span><span class="sxs-lookup"><span data-stu-id="a15f3-102">Marking business objects as safe for scripting</span></span>

<span data-ttu-id="a15f3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a15f3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a15f3-p101">为了帮助确保 Internet 环境安全，需要将由 [RDS.DataSpace](dataspace-object-rds.md) 对象的 [CreateObject](createobject-method-rds.md) 方法实例化的任何业务对象标记为“可安全编写脚本”。首先需要确保在系统注册表的“License”区域中将它们标记为“可安全编写脚本”，然后才能在 DCOM 中使用它们。</span><span class="sxs-lookup"><span data-stu-id="a15f3-p101">To help ensure a secure Internet environment, you need to mark any business objects instantiated with the [RDS.DataSpace](dataspace-object-rds.md) object's [CreateObject](createobject-method-rds.md) method as "safe for scripting." You need to ensure they are marked as such in the License area of the system registry before they can be used in DCOM.</span></span>

<span data-ttu-id="a15f3-p102">若要将业务对象手动标记为“可安全编写脚本”，请创建一个扩展名为 .reg 的文本文件，并在其中包含以下文本。下面的两组数字可以启用“可安全编写脚本”功能：</span><span class="sxs-lookup"><span data-stu-id="a15f3-p102">To manually mark your business object as safe for scripting, create a text file with a .reg extension that contains the following text. The following two numbers enable the safe-for-scripting feature:</span></span>

```vb 
 
[HKEY_CLASSES_ROOT\CLSID\<MyActiveXGUID>\Implemented 
Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}] 
[HKEY_CLASSES_ROOT\CLSID\<MyActiveXGUID>\Implemented 
Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}] 
```

<span data-ttu-id="a15f3-108">其中\<, *MyActiveXGUID* \>是您的业务对象的十六进制 GUID 编号。</span><span class="sxs-lookup"><span data-stu-id="a15f3-108">where \<*MyActiveXGUID*\> is the hexadecimal GUID number of your business object.</span></span> <span data-ttu-id="a15f3-109">将其保存，并通过使用注册表编辑器或双击 Windows 资源管理器中的 .reg 文件将其合并到注册表中。</span><span class="sxs-lookup"><span data-stu-id="a15f3-109">Save it and merge it into your registry by using the Registry Editor or double-clicking the .reg file in Windows Explorer.</span></span>

<span data-ttu-id="a15f3-110">使用打包和部署向导, 可以将在 Microsoft Visual Basic 中创建的业务对象自动标记为 "可安全执行脚本"。</span><span class="sxs-lookup"><span data-stu-id="a15f3-110">Business objects created in Microsoft Visual Basic can be automatically marked as "safe for scripting" with the Package and Deployment Wizard.</span></span> <span data-ttu-id="a15f3-111">当该向导要求您指定安全设置时，请选择\*\*\*\*“Safe for initialization”和\*\*\*\*“Safe for scripting”。</span><span class="sxs-lookup"><span data-stu-id="a15f3-111">When the wizard asks you to specify safety settings, select **Safe for initialization** and **Safe for scripting**.</span></span>

<span data-ttu-id="a15f3-p105">在最后一步，“应用程序安装向导”会创建一个 .htm 文件和一个 .cab 文件。然后，您可以将这两个文件复制到目标计算机上，并双击该 .htm 文件以加载相应的页面并正确注册服务器。</span><span class="sxs-lookup"><span data-stu-id="a15f3-p105">On the last step, the Application Setup Wizard creates an .htm and a .cab file. You can then copy these two files to the target computer and double-click the .htm file to load the page and correctly register the server.</span></span>

<span data-ttu-id="a15f3-114">由于默认情况下, 业务对象将安装在\\windows\\system32 Occache 目录中, 因此将其移动到\\windows system32 目录并更改\*\*HKEY\_类\_根\\CLSID\\ \*\*\< \*\* MyActiveXGUID\>InprocServer32 注册表项以匹配正确的路径。\*\*\*\* \\</span><span class="sxs-lookup"><span data-stu-id="a15f3-114">Because the business object will be installed in the Windows\\System32\\Occache directory by default, move it to the Windows\\System32 directory and change the **HKEY\_CLASSES\_ROOT\\CLSID\\**\<*MyActiveXGUID*\>\\**InprocServer32** registry key to match the correct path.</span></span>


> [!NOTE]
> <span data-ttu-id="a15f3-p106">标记为“可安全编写脚本”或“可安全初始化”的业务对象可以由任何人通过网络实例化和初始化。对于任何自定义业务对象，都不得随意设计和实现。这样的对象不得公开安全威胁，因为黑客会利用这些威胁来获取对宿主服务器上敏感区域的访问并对其造成危害。</span><span class="sxs-lookup"><span data-stu-id="a15f3-p106">Business objects marked as safe for scripting or safe for initialization can be instantiated and initialized by anyone over the network. Any custom business object must not be designed and implemented casually. It is imperative that such objects do not present a security threat that hackers can explore to gain access to the sensitive area of the hosting server and inflict damages.</span></span>



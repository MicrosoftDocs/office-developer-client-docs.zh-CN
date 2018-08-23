---
title: 表单配置文件 [平台] 部分
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3b9b3dc0-4f82-468b-8e77-0374c5b196f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d86edfb6fcc72c5968a8ff5d9cd739e20e5dec43
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589894"
---
# <a name="form-configuration-file-platforms-section"></a><span data-ttu-id="3566d-103">表单配置文件 [平台] 部分</span><span class="sxs-lookup"><span data-stu-id="3566d-103">Form Configuration File [Platforms] Section</span></span>

<span data-ttu-id="3566d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3566d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3566d-105">**[平台]** 节列出了由此窗体支持的平台的完整集合。</span><span class="sxs-lookup"><span data-stu-id="3566d-105">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="3566d-106">每个平台项包含前缀**平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-106">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="3566d-107">_字符串_，其中_字符串_是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="3566d-107">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="3566d-108">每个字符串对应于单个 **[平台]** 节的**CPU**条目。</span><span class="sxs-lookup"><span data-stu-id="3566d-108">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="3566d-109">每个条目 **[平台]** 节中的定义的引用的后续_平台字符串_ **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-109">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="3566d-110">_平台字符串_**]** 部分如下所示。</span><span class="sxs-lookup"><span data-stu-id="3566d-110">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="3566d-111">**[平台]** 节列出了由此窗体支持的平台的完整集合。</span><span class="sxs-lookup"><span data-stu-id="3566d-111">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="3566d-112">每个平台项包含前缀**平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-112">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="3566d-113">_字符串_，其中_字符串_是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="3566d-113">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="3566d-114">每个字符串对应于单个 **[平台]** 节的**CPU**条目。</span><span class="sxs-lookup"><span data-stu-id="3566d-114">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="3566d-115">每个条目 **[平台]** 节中的定义的引用的后续_平台字符串_ **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-115">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="3566d-116">_平台字符串_**]** 部分如下所示。</span><span class="sxs-lookup"><span data-stu-id="3566d-116">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="3566d-117">**[平台]**</span><span class="sxs-lookup"><span data-stu-id="3566d-117">**[Platforms]**</span></span>
  
<span data-ttu-id="3566d-118">**平台**。</span><span class="sxs-lookup"><span data-stu-id="3566d-118">**Platform**.</span></span> <span data-ttu-id="3566d-119">_字符串_ =  _平台字符串_</span><span class="sxs-lookup"><span data-stu-id="3566d-119">_string_ =  _platform string_</span></span>
  
<span data-ttu-id="3566d-120">以下是 **[平台]** 部分的示例。</span><span class="sxs-lookup"><span data-stu-id="3566d-120">Following is an example of a **[Platforms]** section.</span></span> 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

<span data-ttu-id="3566d-121">每个 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-121">Each **[Platform.**</span></span> <span data-ttu-id="3566d-122">_平台字符串_**]** 部分包含**CPU**和**OSVersion**两个必填的条目。</span><span class="sxs-lookup"><span data-stu-id="3566d-122">_platform string_ **]** section contains the two required entries, **CPU** and **OSVersion**.</span></span> <span data-ttu-id="3566d-123">**CPU**条目指定处理器和**OSVersion**条目指定操作系统。</span><span class="sxs-lookup"><span data-stu-id="3566d-123">The **CPU** entry specifies the processor, and the **OSVersion** entry specifies the operating system.</span></span> <span data-ttu-id="3566d-124">**CPU**有效值如下表所述。</span><span class="sxs-lookup"><span data-stu-id="3566d-124">Valid **CPU** values are described in the following table.</span></span> 
  
|<span data-ttu-id="3566d-125">**CPU 条目**</span><span class="sxs-lookup"><span data-stu-id="3566d-125">**CPU Entry**</span></span>|<span data-ttu-id="3566d-126">**处理器**</span><span class="sxs-lookup"><span data-stu-id="3566d-126">**Processor**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3566d-127">Ix86</span><span class="sxs-lookup"><span data-stu-id="3566d-127">Ix86</span></span>  <br/> |<span data-ttu-id="3566d-128">Intel 80 条 x86 和奔腾系列处理器，以及从 AMD、 Cyrix、 NextGen 和其他制造商提供的等效处理器。</span><span class="sxs-lookup"><span data-stu-id="3566d-128">Intel 80x86 and Pentium series processors, as well as equivalent processors from AMD, Cyrix, NextGen and other manufacturers.</span></span>  <br/> |
|<span data-ttu-id="3566d-129">MIPS</span><span class="sxs-lookup"><span data-stu-id="3566d-129">MIPS</span></span>  <br/> |<span data-ttu-id="3566d-130">MIPS R4000 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="3566d-130">MIPS R4000 series processors.</span></span>  <br/> |
|<span data-ttu-id="3566d-131">AXP</span><span class="sxs-lookup"><span data-stu-id="3566d-131">AXP</span></span>  <br/> |<span data-ttu-id="3566d-132">数字设备 Corporation Alpha AXP 处理器。</span><span class="sxs-lookup"><span data-stu-id="3566d-132">Digital Equipment Corporation Alpha AXP processor.</span></span>  <br/> |
|<span data-ttu-id="3566d-133">PPC</span><span class="sxs-lookup"><span data-stu-id="3566d-133">PPC</span></span>  <br/> |<span data-ttu-id="3566d-134">Motorola 电源 PC 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="3566d-134">Motorola Power PC series processors.</span></span>  <br/> |
|<span data-ttu-id="3566d-135">M68</span><span class="sxs-lookup"><span data-stu-id="3566d-135">M68</span></span>  <br/> |<span data-ttu-id="3566d-136">Mororola 68 x 00 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="3566d-136">Mororola 68x00 series processors.</span></span>  <br/> |
   
<span data-ttu-id="3566d-137">**OSVersion**有效值如下表所述。</span><span class="sxs-lookup"><span data-stu-id="3566d-137">Valid **OSVersion** values are described in the following table.</span></span> 
  
|<span data-ttu-id="3566d-138">**OSVersion 条目**</span><span class="sxs-lookup"><span data-stu-id="3566d-138">**OSVersion Entry**</span></span>|<span data-ttu-id="3566d-139">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="3566d-139">**Operating System**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3566d-140">Win3.1</span><span class="sxs-lookup"><span data-stu-id="3566d-140">Win3.1</span></span>  <br/> |<span data-ttu-id="3566d-141">Windows 3.1 和 Windows for 工作组 3.11。</span><span class="sxs-lookup"><span data-stu-id="3566d-141">Windows 3.1 and Windows for Workgroups 3.11.</span></span>  <br/> |
|<span data-ttu-id="3566d-142">WinNT3.5</span><span class="sxs-lookup"><span data-stu-id="3566d-142">WinNT3.5</span></span>  <br/> |<span data-ttu-id="3566d-143">Windows NT 3.5 或更低。</span><span class="sxs-lookup"><span data-stu-id="3566d-143">Windows NT 3.5 or lower.</span></span>  <br/> |
|<span data-ttu-id="3566d-144">Win95</span><span class="sxs-lookup"><span data-stu-id="3566d-144">Win95</span></span>  <br/> |<span data-ttu-id="3566d-145">Windows 95。</span><span class="sxs-lookup"><span data-stu-id="3566d-145">Windows 95.</span></span>  <br/> |
|<span data-ttu-id="3566d-146">WinNT4.0</span><span class="sxs-lookup"><span data-stu-id="3566d-146">WinNT4.0</span></span>  <br/> |<span data-ttu-id="3566d-147">Windows NT 4.0。</span><span class="sxs-lookup"><span data-stu-id="3566d-147">Windows NT 4.0.</span></span>  <br/> |
|<span data-ttu-id="3566d-148">Mac7</span><span class="sxs-lookup"><span data-stu-id="3566d-148">Mac7</span></span>  <br/> |<span data-ttu-id="3566d-149">Macintosh 系统 7。</span><span class="sxs-lookup"><span data-stu-id="3566d-149">Macintosh System 7.</span></span>  <br/> |
   
<span data-ttu-id="3566d-150">此外， **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-150">Additionally, the **[Platform.**</span></span> <span data-ttu-id="3566d-151">_平台字符串_**]** 节必须包含**文件**或**LinkTo**项。</span><span class="sxs-lookup"><span data-stu-id="3566d-151">_platform string_ **]** section must contain either a **File** or **LinkTo** entry.</span></span> <span data-ttu-id="3566d-152">**文件**项列出的窗体服务器应用程序可执行文件的表单库维护和窗体启动时加载到磁盘缓存中的新子目录。</span><span class="sxs-lookup"><span data-stu-id="3566d-152">The **File** entry lists the form server application executable file that the form library maintains and loads into a new subdirectory in the disk cache when the form is launched.</span></span> <span data-ttu-id="3566d-153">如果改为使用**LinkTo**条目，则它包含的**文件**信息就摘自该不同的平台字符串的名称。</span><span class="sxs-lookup"><span data-stu-id="3566d-153">If a **LinkTo** entry is used instead, it contains the name of a different platform string from which the **File** information is taken.</span></span> <span data-ttu-id="3566d-154">这很有用，如果一个版本的窗体支持多个平台。</span><span class="sxs-lookup"><span data-stu-id="3566d-154">This is useful if one version of a form supports multiple platforms.</span></span> 
  
<span data-ttu-id="3566d-155">每次使用的**文件**项时使用的**注册表**项，它标识存储窗体服务器应用程序的可执行文件的表单库的注册表项。</span><span class="sxs-lookup"><span data-stu-id="3566d-155">The **Registry** entry is used whenever the **File** entry is used, it identifies the registry key for the form library where the executable file for the form server application is stored.</span></span> <span data-ttu-id="3566d-156">前加反斜杠 (\) 的字符串被放置注册表的根目录。</span><span class="sxs-lookup"><span data-stu-id="3566d-156">Strings preceded by a backslash ( \ ) are placed at the root of the registry.</span></span> <span data-ttu-id="3566d-157">字符串反斜杠前面没有处于 HKEY_CLASSES_ROOT\CLSID\ _GUID_\ 注册表项，其中_GUID_是窗体的**GUID** 。</span><span class="sxs-lookup"><span data-stu-id="3566d-157">Strings not preceded by a backslash are placed in the HKEY_CLASSES_ROOT\CLSID\  _GUID_\ registry key, where  _GUID_ is the **GUID** of the form.</span></span> <span data-ttu-id="3566d-158">可以使用字符"%d"，以指示从中读取窗体配置文件的目录的路径名。</span><span class="sxs-lookup"><span data-stu-id="3566d-158">The characters "%d" can be used to indicate the pathname of the directory from which the form configuration file has been read.</span></span> <span data-ttu-id="3566d-159">这是用于指定使用相对于窗体配置文件的路径名其他文件。</span><span class="sxs-lookup"><span data-stu-id="3566d-159">This is useful for specifying other files with pathnames relative to the form configuration file.</span></span> <span data-ttu-id="3566d-160">可以通过使用作为前缀跟任何其他文本的文件或注册表中指定**多个文件**或**注册表**项。</span><span class="sxs-lookup"><span data-stu-id="3566d-160">**Multiple File** or **Registry** entries can be specified by using File or Registry as a prefix followed by any other text.</span></span> <span data-ttu-id="3566d-161">格式为 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-161">The format for the **[Platform.**</span></span> <span data-ttu-id="3566d-162">_平台字符串_**]** 部分是：</span><span class="sxs-lookup"><span data-stu-id="3566d-162">_platform string_ **]** section is:</span></span> 
  
- <span data-ttu-id="3566d-163">**[Platform。**</span><span class="sxs-lookup"><span data-stu-id="3566d-163">**[Platform.**</span></span> <span data-ttu-id="3566d-164">_平台字符串_**]**</span><span class="sxs-lookup"><span data-stu-id="3566d-164">_platform string_ **]**</span></span>
    
- <span data-ttu-id="3566d-165">**CPU** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="3566d-165">**CPU** =  _string_</span></span>
    
- <span data-ttu-id="3566d-166">**OSVersion** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="3566d-166">**OSVersion** =  _string_</span></span>
    
- <span data-ttu-id="3566d-167">**文件** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="3566d-167">**File** =  _path_</span></span>
    
- <span data-ttu-id="3566d-168">**LinkTo** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="3566d-168">**LinkTo** =  _string_</span></span>
    
- <span data-ttu-id="3566d-169">**注册表** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="3566d-169">**Registry** =  _string_</span></span>
  
<span data-ttu-id="3566d-170">以下是两个示例 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-170">The following are two example **[Platform.**</span></span> <span data-ttu-id="3566d-171">_平台字符串_**]** 各节，一个使用的**文件**项，一个使用**LinkTo**条目。</span><span class="sxs-lookup"><span data-stu-id="3566d-171">_platform string_ **]** sections, one using the **File** entry and one using the **LinkTo** entry.</span></span> 
  
```cpp
[Platform.NTx86]
CPU = ix86
OSVersion = WinNT3.5
File = \helpdesk.exe
Registry = Local Server = %d\helpdesk.exe
[Platform.Win95]
CPU = ix86
OSVersion = Win95
LinkTo = NTx86

```

<span data-ttu-id="3566d-172">**[平台。**</span><span class="sxs-lookup"><span data-stu-id="3566d-172">The **[Platform.**</span></span> <span data-ttu-id="3566d-173">_平台字符串_到本地窗体库中，添加窗体时安装程序已设置为在 OLE 注册表中的处理程序的部分名为可用的本地存储到构成的邮件类处理的文件，并已完成，则假定其值时，将忽略 **]** 节OLE 系统注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="3566d-173">_platform string_ **]** section is ignored when adding a form to the local form library, when it is assumed that the installer has placed the files constituting the message class handler into available local storage as named in the handler's section in the OLE registry, and has done the OLE registration in the system's registry.</span></span> 
  


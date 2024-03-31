# UAC 和管理员模式

UAC（[用户帐户控制](http://en.wikipedia.org/wiki/User_Account_Control)）是 Windows 的一项安全功能。它旨在通过允许管理员操作由访问权限的临时提升来执行，从而让作为标准用户运行变得更加实用。

在 UAC 启用时（这是默认状态），用户和他们启动的程序默认情况下将拥有标准用户权限。这意味着重要的操作系统位置（如 *Windows* 文件夹）和注册表项会受到意外或恶意修改的保护——为了修改这些位置，您需要通过 UAC 提示来“提升”任务。

![](/Manual/images/media/13/user_account_control.png)

### 资源管理器被区别对待

不幸的是，Microsoft 稍稍[搞砸了](http://www.pretentiousname.com/opus9/page4.html#vistauac)资源管理器中 UAC 的实现。人们广泛嘲笑 Vista，因为它需要点击过多的 UAC 提示才能执行例程或日常任务。仅仅创建一个文件夹就会产生四个单独的提示，导致许多人直接关闭 UAC。

自 Windows 7 起，Microsoft 对此批评反应过度，大幅降低了 UAC 的强度——不幸的是，这是以牺牲系统安全性为代价的。默认的 UAC 设置（使用[白名单](http://www.pretentiousname.com/misc/win7_uac_whitelist2.html) 来防止资源管理器和其他 Windows 组件出现任何 UAC 提示）将其简化为安全系统的表象——同时，对没有能力列入白名单的其他第三方工具不利。

我们一直将 UAC 视为一项值得称赞（虽然执行得很差）的尝试，以提高 Windows 的安全性，我们建议在 Windows 安全设置中将其设置为 **始终通知**。Opus 本机支持 UAC，比资源管理器更合理的方式，您不会发现使用 Opus 执行管理任务困难或烦人。

### 在 Opus 中执行管理任务

在受保护的位置（如 *C:\Program Files*）执行文件操作时，Opus 将显示如上图所示的 UAC 提示。它非常智能——它只会针对每项功能提示一次，这与资源管理器有所不同，资源管理器有时会针对一项操作最多提示四次。

### 在一段时间内提升

如果您要执行多项管理任务，您可以使用 **管理员模式** 功能来临时提升当前的文件窗口。

要激活管理员模式，请单击默认工具栏上的 **Admin** 按钮。Opus 将显示一个对话框，让您可以指定一个超时，在此超时后自动停用管理员模式。这是出于安全原因，因为它避免了无意中让文件窗口提升的时间超过必要的时间的风险。

![](/Manual/images/media/13/admin_mode_dialog.png)

选择超时，然后单击确定。然后，Opus 会显示一个 UAC 提示以提升，在此之后，文件窗口本身将在指定的时间段内保持提升（或直到您手动关闭模式）。窗口的标题栏将变为 **管理员** 以表示管理员模式已生效。

（请注意，如果您在标题栏中看到 **ADMINISTRATOR**，则表示整个进程已提升——我们[不建议](https://resource.dopus.com/t/why-not-to-run-opus-as-administrator-under-uac/9102)这样做。）

您在管理员模式文件窗口中执行的任何操作都会自动提升——无需显示任何进一步的 UAC 提示。但请注意，您从该文件窗口启动的任何程序也会被提升。

### 在功能中提升

您可以配置工具栏按钮或热键启动外部程序，以使用 **@admin** [命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md) 启动提升的程序。
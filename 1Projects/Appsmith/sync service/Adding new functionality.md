need to follow below steps to add a new functionality to sync service
- [ ] interface
- [ ] implementation
- [ ] dependency injection
- [ ] controller
### create an interface
```c#
namespace YourNamespace.Contract
{
    public interface IAppsmithOperations
    {
        Task<BaseEntity> Add();
        Task<BaseEntity> Update();
        Task<BaseEntity> Delete();
    }
}

```

### create implementation
```c#
using System.Threading.Tasks;

namespace YourNamespace.Service
{
    public class AppsmithOperationsService : IAppsmithOperations
    {
        public async Task<BaseEntity> Add()
        {
            // Logic for adding Appsmith resources
            return await Task.FromResult(new BaseEntity { /* Populate as needed */ });
        }

        public async Task<BaseEntity> Update()
        {
            // Logic for updating Appsmith resources
            return await Task.FromResult(new BaseEntity { /* Populate as needed */ });
        }

        public async Task<BaseEntity> Delete()
        {
            // Logic for deleting Appsmith resources
            return await Task.FromResult(new BaseEntity { /* Populate as needed */ });
        }
    }
}

```

### dependency injection
```c#
using Autofac;

namespace YourNamespace.Service
{
    public class AppsmithModule : Module
    {
        protected override void Load(ContainerBuilder builder)
        {
            builder.RegisterType<AppsmithOperationsService>()
                   .As<IAppsmithOperations>()
                   .InstancePerLifetimeScope();
        }
    }
}

```
also add to `startup.cs`
```c#
builder.RegisterModule(new AppsmithModule());
```
### expose through controller
```c#
using Microsoft.AspNetCore.Mvc;
using System.Threading.Tasks;

namespace YourNamespace.Controllers
{
    [Route("api/[controller]")]
    [ApiController]
    public class AppsmithController : ControllerBase
    {
        private readonly IAppsmithOperations _appsmithOperations;

        public AppsmithController(IAppsmithOperations appsmithOperations)
        {
            _appsmithOperations = appsmithOperations;
        }

        [HttpPost("add")]
        public async Task<IActionResult> Add()
        {
            var result = await _appsmithOperations.Add();
            return Ok(result);
        }

        [HttpPut("update")]
        public async Task<IActionResult> Update()
        {
            var result = await _appsmithOperations.Update();
            return Ok(result);
        }

        [HttpDelete("delete")]
        public async Task<IActionResult> Delete()
        {
            var result = await _appsmithOperations.Delete();
            return Ok(result);
        }
    }
}

```
# BlazorApp2
BlazorApp2.csproj

Using the template project - Trying to get inject to work.

This goes to the top of a *.razor file:

    @inject IOfTheData TheData
    
And then in the usual  *.cs :

    public class TheData : IOfTheData


But I don't know whether to use 
    Task<IReadOnlyList<Country>>
or
    IEnumerable<Country> All()
  
The FetchData.razor is instructive

    protected override async Task OnInitializedAsync()
    {
        forecasts = await Http.GetJsonAsync<WeatherForecast[]>("sample-data/weather.json");
    }
    
And 'forecasts' is just array 'WeatherForecast[]' of a normal class.

*In short

I don't know what does Blazor expec to see in the @code section?

I have found overrides:

  
    OnAfterRender(bool firstRender)
    OnAfterRenderAsync(bool firstRender)
    OnInitialized()
    OnInitializedAsync()
    OnParametersSet()
    OnParametersSetAsync()
    ShouldRender()
    
    
  
  
  
  

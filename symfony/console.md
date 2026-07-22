# Symfony : Console

## Command

```php
namespace App\Command;

use Symfony\Component\Console\Attribute\AsCommand;
use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

#[AsCommand(name: 'app:report:generate', description: 'Generate reports')]
final class GenerateReportCommand extends Command
{
    protected function execute(InputInterface $input, OutputInterface $output): int
    {
        $output->writeln('<info>Report generated</info>');

        return Command::SUCCESS;
    }
}
```

## Run and Inspect

```bash
php bin/console list
php bin/console app:report:generate
php bin/console help app:report:generate
php bin/console app:report:generate -vvv
```

## Arguments and Options

```php
protected function configure(): void
{
    $this
        ->addArgument('name')
        ->addOption('force', 'f');
}
```

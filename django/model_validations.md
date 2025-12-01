# Validations dans les modèles Django

## clean_fields()

```py
class ExampleModel(models.Model):
    def clean_fields(self, exclude: set = set()):
        errors = {}

        # Possible d'exclure des champs en les ajoutant dans `exclude`

        try:
            super().clean_fields(exclude=exclude)
        except ValidationError as e:
            # On récupère le premier lot d'erreurs s'il y en a
            errors.update(e.message_dict)

        # Possible d'ajouter des validations supplémentaires et d'ajouter des
        # erreurs dans `errors` (mais `validators` et/ou `error_messages`
        # directement sur le champ sont peut-être plus pertinents.)

        if errors:
            raise ValidationError(errors)

```
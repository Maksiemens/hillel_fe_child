# hillel_fe_child
# https://docs.google.com/presentation/d/192Jr3TGddmZV4YOK9wDZQtfD2Y9Y0dbtRQRvQyge6JU/edit?usp=sharing 

# FE Basic HTML Semantic
https://docs.google.com/presentation/d/13mGk_eO5cugOKIeXfUT37Igzg1lJbodXiLaiU0bbc0k/edit?usp=sharing


.checkbox {
  $this: &;
  position: relative;
  display: flex;

  &__label {
    @include font-primary(14px, $color-form-control-text-primary);
    display: inline-flex;
    align-items: center;
    cursor: pointer;
    transition: opacity $time-transition;

    @include for-tablet-portrait-up {
      align-items: flex-start;
    }

    &.is-disabled {
      opacity: 0.5;
      cursor: not-allowed;
      user-select: none;
    }

    &.is-full {
      width: 100%;
      padding: 9px 15px;
      background: $background-color-form-control-primary;
      border: 1px solid $border-color-form-control-border;
      border-radius: $border-radius;
    }

    &.is-invalid {
      border: 1px solid $border-color-form-control-error;
    }
  }

  &__text {
    margin-left: 10px;
  }

  &__input {
    -webkit-appearance: none;
    -moz-appearance: none;
    position: relative;
    width: 20px;
    height: 20px;
    display: flex;
    flex-shrink: 0;
    border: 1px solid $border-color-form-control-border;
    border-radius: 2px;
    background: $background-color-form-control-primary;
    transition: background $time-transition, border-color $time-transition, box-shadow $time-transition;
    cursor: pointer;

    @include for-tablet-portrait-up {
      width: 18px;
      height: 18px;
    }

    &:after {
      content: '';
      display: block;
      position: absolute;
      top: 4px;
      left: 7px;
      opacity: 0;
      width: 5px;
      height: 9px;
      border: 2px solid $color-border-primary;
      border-top: 0;
      border-left: 0;
      transform: rotate(20deg);
      transition: transform $time-transition ease, opacity $time-transition;
      @include for-tablet-portrait-up {
        top: 2px;
        left: 6px;
      }
    }

    &:checked {
      background: $background-color-tertiary;
      border: 1px solid $border-color-form-control-focus;

      &::after {
        opacity: 1;
        transform: rotate(43deg);
        transition: transform 0.6s cubic-bezier(0.2, 0.85, 0.32, 1.2), opacity $time-transition;
      }
    }

    &:disabled {
      opacity: 0.5;
      cursor: not-allowed;
      pointer-events: none;
    }

    &:hover {
      &:not(:checked) {
        &:not(:disabled) {
          border: 1px solid $border-color-form-control-focus;
        }
      }
    }

    &.ng-invalid.ng-touched {
      border: 1px solid $border-color-form-control-error;

      &:focus {
        border: 1px solid $border-color-form-control-error;
      }
    }
  }
}



radio

.radio-button {
  width: 100%;
  display: flex;

  &__label {
    @include font-primary(14px, $color-form-control-text-primary);
    width: 100%;
    display: inline-flex;
    align-items: center;
    cursor: pointer;

    &.is-disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }

    &.is-full {
      padding: 9px 15px;
      background-color: $background-color-form-control-primary;
      border: 1px solid $border-color-form-control-border;
      border-radius: $border-radius;
    }
  }

  &__input {
    -webkit-appearance: none;
    -moz-appearance: none;
    position: relative;
    width: 20px;
    height: 20px;
    display: flex;
    flex-shrink: 0;
    border: 1px solid $border-color-form-control-border;
    border-radius: 50%;
    background: $background-color-primary;
    transition: background 0.3s, border-color 0.3s, box-shadow 0.2s;
    cursor: pointer;

    &:after {
      @include pseudo;
      top: 50%;
      left: 50%;
      width: 18px;
      height: 18px;
      border-radius: 50%;
      background: $background-color-tertiary;
      opacity: 0;
      transform: translate(-50%, -50%) scale(0);
      transition: transform 0.3s ease, opacity 0.3s;
    }

    &:checked {
      border: 1px solid $color-border-primary;

      &::after {
        opacity: 1;
        transform: translate(-50%, -50%) scale(0.7);
      }
    }

    &:disabled {
      opacity: 0.5;
      cursor: not-allowed;

      &:checked {
        background-color: $background-color-quaternary;
        border: 1px solid $color-border-primary;
      }
    }

    &:hover {
      &:not(:checked) {
        &:not(:disabled) {
          border: 1px solid $color-border-primary;
        }
      }
    }
  }

  &__text {
    &.is-active {
      margin-left: 10px;
    }
  }
}

